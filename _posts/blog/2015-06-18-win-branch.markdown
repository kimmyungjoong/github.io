---
layout: post
title: "Windows 분기 처리"
date: 2016-06-18
author: MJKIM
categories:
- blog
- html/css
- javascript

img: post02.jpg
thumb: thumb02.jpg
---

사용자가 윈도우 환경일때 .win 클래스를 추가하여 분기 처리

---

**아래와 같은 코드로 쉽게 분기 처리**

      <script>
        document.documentElement.className += (
          (window.navigator.appVersion.indexOf("Win") != -1) ? 'win' : ''
      );
      </script>


[hampden]: https://github.com/jekyll/jekyll

<div id="disqus_thread"></div>
<script>

/**
 *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
 *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables */
/*
var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = '//http-kimmyungjoong-github-io.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
