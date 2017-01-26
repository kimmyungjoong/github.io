---
layout: post
title: "링크 및 포커스 확인"
date: 2014-04-25
author: MJKIM
categories:
- blog
- html/css
- javascript

img: post01.jpg
thumb: thumb01.jpg
---

북마크를 사용하여 링크 또는 북마크를 확인하여 보자
마크업 작업을 하다 보면은 디자이너나 기획자가 링크 영역의 크기에 대한 부분을 언급하지 않을때가 자주 일어난다
그때 사용하면 유용한 툴이다. 협업 부서에 보여주기도 쉽고, 내가 작업을 할때 링크 영역이 얼마나 잡혀있는지
한눈에 볼수 있기 때문에 수정이 아주 용이하다.

---

**1. 아래와 같이 크롬에서 북마크바를 활성화 합니다.**

![북마크바 활성화](/assets/img/blog/link01.png)

**2. 북마크바에서 마우스 오른쪽 클릭해서 페이지 추가 버튼 클릭!**

![북마크바 페이지 추가](/assets/img/blog/link02.png)

**2. 페이지 추가에서 url 부분에 아래 코드 입력, 이름은 사용자가 정의**

![북마크바 페이지 추가](/assets/img/blog/link03.png)


    javascript:(function(){
        var jsf=document.createElement('SCRIPT');
        jsf.type='text/javascript';
        jsf.src='https://ajax.googleapis.com/ajax/libs/jquery/1.9.0/jquery.min.js';
        document.getElementsByTagName('body')[0].appendChild(jsf);
        var jsf2=document.createElement('SCRIPT');
        jsf2.type='text/javascript';
        jsf2.src='http://kimmyungjoong.github.io/assets/js/click-check.js';
        document.getElementsByTagName('body')[0].appendChild(jsf2);
      })();







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
