# Unity 2021.3 HDRP DLSS & AMD FSR Fixes

This repository is an up to date version of official Unity Graphics repository on 2021.3/staging branch; including a custom DLSS injection point to make DLSS run after post process. 

Unity Graphics repostirory is here: https://github.com/Unity-Technologies/Graphics/

The branch I'm using for this repository 2021.3/staging is here: https://github.com/Unity-Technologies/Graphics/tree/2021.3/staging

# DLSS & AMD FSR fix?
In Unity 2021.3 LTS and HDRP 12.1.x series, there is a bug that makes the Custum Post Processes and Custom Pass effects render at a quarter resolution, making them unusable if you're using any Custom Post Process.
Since I had some custom passes and custom post processes in my project, DLSS was unusable. However, without DLSS or AMD FSR, it was hard to support 4K with a reasonable performance.
So I had to resort to this, getting related fixes from various commits on official Unity repositories.

Mind that this issue is fixed in newer Unity and HDRP versions, so this is only useful if you're stuck at Unity 2021.3 LTS like me.

# What's the gain?
Since DLSS & AMD FSR now works after post process, performance gain is incredible. At 4K, default Unity HDRP scene gives ~16 FPS in Editor. With DLSS Max Quality enabled, it gives ~50 FPS.

# What's the downside?
Since DLSS & AMD FSR now works after post process, upscale algorithm now upscales the post process too. For example, if you're using a simple gaussian blur, with DLSS, blur becomes a mess.

# More info?
Take a look at my blog post for more information, use cases, screenshots and comparisons.

Turkish: https://blog.tanshaydar.com/?p=27418

English: https://en.tanshaydar.com/?p=1002
