---
layout: post
published: false
title:  "깃허브 블로그 로컬 실시간 적용확인"
---


<!-- 
영상 : https://www.youtube.com/watch?v=0TeHUqSAb6Q&list=PLIMb_GuNnFwfQBZQwD-vCZENL5YLDZekr&index=3
-->

몇가지 설치  
minimal mistakes  
https://mmistakes.github.io/minimal-mistakes/docs/installation/  
안에  
Install dependencies항목에   
official documentation 눌러스 사이트 이동  
https://jekyllrb.com/docs/  
3가지 설치

1번 Install all prerequisites 클릭으로 이동  
Requirements에 각각 클릭해서 설치  

Ruby > windows 버전 다운    
WITH DEVKIT 제일 위에거 설치  
동의 > 다른거 건드리지 말고 설치  
실행화면 뜨면 3번  
설치 완료 후 종료  

windows + r > "cmd"  
gem install jekyll  
설치 완료 후  
gem install bundler설치  

블로그 설치폴더(io안에서)에서 shift + 우클릭 > 여기에 power shell 창 열기  
ls (폴더내 파일 확인)  
bundle install

[!] There was an error parsing `Gemfile` :  에러시  
Gemfile을 vscode로 열기  
gemspec > gemspecs 으로 변경  
다시 bundle install 실행  
댓글가운데 답이 있었음  

에러  
1) bundle install시에 [!] There was an error parsing `Gemfile` 에러 발생시 
- Gemfile에 gemspec을 gemspecs로 변경.

2) bundle exec jekyll serve시 "block in replace_bin_path" 에러 발생시
- Gemfile에 gem "minimal-mistakes-jekyll" 추가.
- power shell에 "bundle" 입력.
- 이후 다시 "bundle exec jekyll serve" 실행.

webrick 에러시  
bundle add webrick  

웹페이지 실행  
localhost:4000  

에러  
 Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?  
해결  
gem install wdm 실행  
gem 'wdm', '>= 0.1.0' 를 gemfile 에 추가  

bundle exec jekyll serve 실행 하기전에 온라인 서버와 포스팅 상태가 같아야 하는 것 같다  
bundle exec jekyll serve --livereload 실행명령도 있음  

 Build Warning: Layout 'post' requested in _posts/2022-03-10-vscode_test.md does not exist. 에러는 아직 미해결   
https://gist.github.com/MichaelCurrin/5c8c45a86bcf53d7b49a7763c02943b1  
여기 내용 참고 할 만 한듯  
https://bundler.io/ 확인  

Incremental build: disabled. Enable with --incremental  











