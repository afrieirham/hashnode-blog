## How to use your domain and subdomain with Hashnode and Vercel

Yesterday I ran into a problem when I try to connect my domain to Hashnode and use a subdomain on Vercel. Thankfully, everything is resolved after I reach out to Sandeep on Twitter.

Here's the tweet.

%[https://twitter.com/afrieirham_/status/1418174381533003779]

If you're planning to use your naked domain (or root domain) on Hashnode and you have a project on Vercel using a subdomain from the same domain – please read this first.

# The Issue 
Hashnode uses Vercel, and when you want to connect your root domain to your Hashnode blog, you will need to delegate it to Hashnode's Vercel account.

Again, if you're not planning to use any subdomain (on Vercel) from the domain you use on Hashnode, there's no problem.

However, I want to use afrieirham.com for my Hashnode blog, and I want to use bukugraduan.afrieirham.com on my Vercel project.


But I get this error 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1627019309729/fQA9_qIVo.png)

Because what essentially happens is you're trying to use the same domain with 2 different Vercel account; Hashnode's and yours.

# The solution

If you've already facing the same issue, you might want to contact Hashnode to delete your domain from their Vercel account, then follow these steps.

1. Use www subdomain for your Hashnode account.
2. Redirect your root domain to point to your www subdomain.
3. You can now use any subdomain on your Vercel account.

This way, you'll only delegate www subdomain to Hashnode and you'll keep your root domain on your Vercel account.

# Conclusion
I want to again thank [Sandeep](https://twitter.com/Sandeepg33k) for his help. He's the one who get in touch with Vercel regarding this issue.

The solution I'm sharing here today is the suggestion from Vercel's team, so I would like to thank them as well.

This is what they have to say,
> It will be supported in the future. At this moment, however, it is indeed an edge case that we are not prepared yet. –Vercel
