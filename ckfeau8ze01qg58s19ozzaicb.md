## FYP-DevLog 011

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/r31g7crr7flgvosu98f4.png)

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/38bpvhiif9lwt93kwun8.png)

Today I managed to display the user's name on the dashboard with React Context, and while I'm at it I also store the role data in the same UserContext to display it.

With the role data, I can use that state to give access or limit action to a certain user based on their role.

But before I could do that, I realized that whenever I refresh the page, the state is reset. I'm not sure how why is that. To be honest, I might implement react context wrong altogether.

This is my UserContext
```javascript
import React, { createContext, useState } from 'react'

// Create context
export const UserContext = createContext()

// Provider component
export function UserProvider({ children }) {
  const [username, setUsername] = useState('')
  const [role, setRole] = useState('')

  const value = { username, setUsername, role, setRole }

  return <UserContext.Provider value={value}>{children}</UserContext.Provider>
}

```

And then in the App.js I wrap it with UserProvider
```javascript
function App() {
  return (
    <React.Fragment>
      <Router>
        <Switch>
          <UserProvider>
            <PublicRoute exact path='/' component={Login} />
            <PublicRoute
              exact
              path='/forgot-password'
              component={ForgotPassword}
            />
            <ProtectedRoute path='/dashboard' component={Dashboard} />
          </UserProvider>
        </Switch>
      </Router>
    </React.Fragment>
  )
}
```

Lastly, in the Topbar component, I get the data with useContext and display it.

```javascript
import React, { useContext } from 'react'

import axios from 'axios'
import store from 'store'
import { withRouter } from 'react-router'
import { UserContext } from '../context/UserContext'

function Topbar(props) {
  const { username, role } = useContext(UserContext)

  return (
    <Navbar
      style={{ width: '100%' }}
      bg='light'
      expand='lg'
      className='justify-content-end'
    >
      <Form inline>
        <FormControl type='text' placeholder='Search' className='mr-3' />
      </Form>

      <DropdownButton
        id='dropdown-item-button'
        title={`${username} (${role})`}
        variant='white'
        alignRight
      >
        <Dropdown.Item>Profile</Dropdown.Item>
        <Dropdown.Item>Change Password</Dropdown.Item>
        <Dropdown.Divider />
        <Dropdown.Item onClick={logout}>Logout</Dropdown.Item>
      </DropdownButton>
    </Navbar>
  )
}

export default withRouter(Topbar)

```

I'm not really sure why this happens, again I might use the react context wrong from the beginning. But if any of you know why this happens and knows how to solve it. Feel free to comment down. I appreciate it.

That's all for today, thanks for reading.