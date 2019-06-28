---
layout: post
title: Github로 블로그만들기(2)-Jekyll개발환경을 만들자!
---
## Github계정생성
자신의 Jekyll기반 블로그를 웹에 업로드 하기 위해서는 자신의 Github아이디가 필요하다. <br />[Github 바로가기](http://github.com/)<br />
1. > ![github-signup(1)](/../public/images/post.2019-06-29/github-signup(1).PNG) 사이트의 <i class="highlight-yellow">Sign up for Github</i>를 클릭한다.
2. > ![github-signup(2)](/../public/images/post.2019-06-29/github-signup(2).PNG) <i class="highlight-blue">Username</i>과<i class="highlight-blue">Email address</i>,<i class="highlight-blue">Password</i>를 입력하고 밑의 '검증'을 한 후 continue를 누른다. <br /><strong class="highlight-red">※Username은 추후 사이트를 제작할 때 [Username].github.io 같은 형식으로 사용되므로 신중히 정하자!</strong>
3. > ![github-signup(3)](/../public/images/post.2019-06-29/github-signup(3).PNG)*Pro*와 *Free*중 하나를 선택할 수 있다. 물론 *Pro*는 몇가지 이점이 있으나 그 기능들은 추후에 정말 필요할 때 구입하도록 하고, 일단은 *Free*를 선택한 후, continue를 한다.
4. > ![github-signup(4)](/../public/images/post.2019-06-29/github-signup(4).PNG)자신의 프로그래밍 경험과 Github용도를 체크한 후 제출 또는 스킵을 한다.
5. > ![github-signup(5)](/../public/images/post.2019-06-29/github-signup(5).PNG)이메일을 확인하면 Github가입이 끝나게 된다.

## Ruby와 Jekyll, Bundler설치하기
Jekyll은 Ruby라는 언어를 기반으로 실행이 된다. Ruby공식사이트에 가서 Ruby를 다운받자. <br />[Ruby 공식 사이트](https://www.ruby-lang.org/en/downloads/)
1. > ![install-ruby(1)](/../public/images/post.2019-06-29/install-ruby(1).PNG) 웹사이트 중간에보이는 <i class="highlight-yellow">RubyInstaller</i>를 클릭한다.
2. > ![install-ruby(2)](/../public/images/post.2019-06-29/install-ruby(2).PNG)큼직하게 자리하고 있는 <i class="highlight-yellow">DOWNLOAD</i>를 클릭!
3. > ![install-ruby(3)](/../public/images/post.2019-06-29/install-ruby(3).PNG)*WITH DEVKIT*카테고리에서 highlight처리된 <i class="highlight-yellow">'Ruby+Devkit ~~'</i>를 클릭하면 설치가 진행된다. <br /><strong class="highlight-red">※설치 중 path를 추가하라는 checkbox를 check해서 설치해야 한다.※</strong><br /><strong class="highlight-red">※설치 과정에서 마지막에 ridk install을 설치해야 한다. 이는 나중에 'Gems'를 설치하는데 필요하다.※</strong>
4. > <div class="colorscripter-code" style="color:#010101; font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; position:relative !important; overflow:auto"><table class="colorscripter-code-table" style="margin:0; padding:0; border:none; background-color:#fafafa; border-radius:4px;" cellspacing="0" cellpadding="0"><tr><td style="padding:6px; border-right:2px solid #e5e5e5"><div style="margin:0; padding:0; word-break:normal; text-align:right; color:#666; font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; line-height:130%"><div style="line-height:130%">1</div></div></td><td style="padding:6px 0"><div style="margin:0; padding:0; color:#010101; font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; line-height:130%"><div style="padding:0 6px; white-space:pre; line-height:130%">gem&nbsp;install&nbsp;jekyll&nbsp;bundler</div></div></td><td style="vertical-align:bottom; padding:0 2px 4px 0"><a href="http://colorscripter.com/info#e" target="_blank" style="text-decoration:none; color:white"><span style="font-size:9px; word-break:normal; background-color:#e5e5e5; color:white; border-radius:10px; padding:1px">cs</span></a></td></tr></table></div> 위와 같은 명령어를 윈도우의 콘솔, cmd창에 입력해서 jekyll와 bundler를 다운받는다.

<h1 style="font-family: 'Black Han Sans';">이렇게 윈도우에서 Jekyll개발환경이 완성되었다! 다음 포스트에서는 Jekyll 샘플 사이트를 제작해 볼 것이다!</h1>