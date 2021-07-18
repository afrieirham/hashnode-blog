## FYP-DevLog 004

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/2y5psef3vnw0bgjsvgrf.png)

This is what I did today, seems pretty simple but it took me awhile especially the toggle switch. Well to be fair it has been a almost 3 months since I use React so that is why it took me some time to familiarize myself again. 

I also did some changes (by changes I mean a single line of code) in my API response. 

Other than that, there was nothing much today. Took quite a time to fix the toggle switch bug which I still didn't quite understand how it works.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/jvt633p9wtqs5spk9sgz.png)

Referring to the codes, all I did was update the checkin state with `setCheckin(!checkin)` and in line 8 I use the checkin to make the request body for the PUT request.

Somehow the checkin in line 8 is not coming from the state that I have changed in line 4. The fix is quite simple, I changed it to `const requestBody = { is_checkin: !checkin }`

But I don't know why it acts that way. I thought after you have update the state with `setCheckin(!checkin)` it will automatically use the latest state when you reference it later but somehow it didn't work like that.

Note that I'm still quite new to React especially React Hooks. Feel free to correct me and give me some explanation about this. 

Again, I might be wrong (I probably am) about this and that is exactly how it works. But for now I just don't quite understand.

That's all for today and if you make it up to this point, thank you for reading. I appreciate it.

