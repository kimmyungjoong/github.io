---
layout: post
title: "Grunt markup-file-index"
date: 2017-02-06
author: MJKIM
categories:
- blog
- grunt

img: post03.jpg
thumb: thumb03.jpg
---

## Grunt를 사용하여 markupfile index 만들기
---
목적 및 목표
- UI 개발 완료 후 인덱스 파일을 제작하는 시간을 감소 시키자
- UI 개발 산출물을 한눈에 쉽게 파악하자
- 작업 파일이 많을 경우 협업 부서에 심플하게 리스팅된 파일로 공유하자

문제점
- 현재 UI 개발 산출물을 개인이 작업한 파일만 관리 (다른 작업자가 history를 알지 못함)
- 현재 html 파일은 서버에 업로드 되지 않아 전체 산출물 파악이 어려움 (html 파일은 서버 업로드 제외 대상)
- UI 개발 완료 후 파일의 양이 많을 경우 index를 많드는 시간이 개발 완료 시간 외에 소요됨. (수정된 파일이나 추가 파일이 있을 경우 index 파일도 같이 수정 및 추가 해야됨.)

---

### 환경 셋팅 및 실행과정 
<br>

**1. nvm 설치**

      curl https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash

<br>

**2. 경로 설정 및 업데이트**

      source ~/.bash_profile
      
<br>

**3. Node.js 설치**

      nvm install stable
      
<br>

**4. Grunt-cli 설치**

      npm install -g grunt-cli
      
<br>

**5. 프로젝트 폴더(작업폴더)에 grunt 설치**

      npm install grunt --save-dev
      
<br>

**6. package.json 파일 생성**
```
  npm init
```      
*정보 입력 시 무시하고 enter 다다닥! 마지막에 yes 입력*      
<br>

**7. index 생성 모듈 설치**

      npm install grunt-markupfileindex --save-dev
      
<br>

**8. 프로젝트 폴더(작업 폴더)내에 나만의 스타일로 커스텀 진행**

커스텀 파일위치 및 목록
- node_modules/grunt-markupfileindex/tasks/markupfileindex.js
- node_modules/grunt-markupfileindex/tpl/tpl.html

<br>

**9. Gruntfile.js 파일 생성**

아래 코드 입력하여 생성

```
  'use strict';

  module.exports = function(grunt) {
    grunt.initConfig({
        pkg: grunt.file.readJSON('package.json'),
        markupfileindex: {
          options: {
            show_date : true,
            filename: '@index.html',
            title:'UI개발 마크업 산출물',
            include_folder : ['includes', 'inc', 'testInc'],
            file_sort : 'asc',
            file_sort_key : 'title',
            group_sort : 'asc',
            path_replace : '^../',
          },
          index: {
            files: [{
              expand : true,
              cwd : './',
              src: ['**/*.{html,php}', '!**/node_modules/**', '!**/.*/**'],
              dest: './'
            }]
          }
        }
    });
     
    grunt.loadNpmTasks('grunt-markupfileindex');
    // Default task(s).
    grunt.registerTask('index', ['markupfileindex']);

  };
```
<br>

**10. .gitignore 파일 생성**

*아래 코드를 입력하여 생성 (해당 파일 및 폴더는 서버에 업로드 되지 않는다.)*

```
  node_modules
  Gruntfile.js
  package.json
  .gitignore
```      
<br>

**11. src 폴더를 생성하여 src 폴더 내에 파일 작업 및 관리**

- 예) work(작업 폴더)/src/파일.html

<br>

**12. 프로젝트 폴더(작업 폴더) 터미널에서 아래 명령어 입력**

- 예) work(작업폴더) 위치

```
  grunt index
```
<br>

**13. @index.html 파일이 생성 되었는지 확인**

- 예) work(작업 폴더)/@index.html

<br>

**14. The end**

<br>

**Tip. 타이틀을 가져오는 HTML 코드 안내**

```
  <title>[그룹명] 타이틀명</title>
  <title>타이틀명</title>

  <title> 값을 읽어옴
```


<br>
<br>

**출처**  

- [https://www.npmjs.com/package/grunt-markupfileindex](https://www.npmjs.com/package/grunt-markupfileindex)

- [https://github.com/chosungmin/grunt-markupfileindex](https://github.com/chosungmin/grunt-markupfileindex)


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
