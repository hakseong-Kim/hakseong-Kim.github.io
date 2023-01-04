### Hexo 설치
Hexo는 Node.js 기반이기 때문에 Node.js가 설치되어있어야 한다.

1. 글로벌하게 hexo-cli 설치한다.
$ npm install hexo-cli -g

2. hexo로 Blog 프로젝트를 만들어준다.
$ hexo init blog
$ cd blog
$ npm install

3. 테마적용을 위해 git clone 진행 (필자는 icarus 테마를 선택)
$ git clone https://github.com/ppoffice/hexo-theme-icarus.git

###hexo 테마
4. themes 폴더안에 clone 받은 테마의 폴더명을 hexo-theme-icarus -> icarus로 변경해준다.
5. 루트 경로에서 _config.yml 파일을 아래처럼 수정해준다.

6. 테마에 필요한 npm 패키지들을 설치해준다. (icarus 경우 아래 패키지들이 필요함)
$ npm install --save bulma-stylus hexo-component-inferno hexo-renderer-inferno inferno inferno-create-element

7. hexo s 명령어로 로컬에서 테마가 적용됬는지 확인
$ hexo s 

###GitHub Pages
깃헙 페이지를 이용해 블로그를 배포하기 위해 우선 Repository를 생성해둔다.

"GitHub사용자이름".github.io 로 Repository를 생성해주면 
https://사용자이름.github.io/ 블로그 주소로 사용 가능

###Hexo-Deployer-Git
Hexo에서 Git으로 정적파일을 생성후 편하게 배포하기위한 패키지를 받아준다.

$ npm install --save hexo-deployer-git
Github에서 만들어둔 Repository의 Clone 주소를 Hexo 프로젝트 설정파일에 적어준다.

_config.yml
deploy:
  type: git
  repo: 저장소 주소(예: https://github.com/사용자계정/사용자계정.github.io.git)
  branch: master

publish용 정적파일 생성
$ hexo generate

Github 배포
$ hexo deploy

동시 생성 & 배포
$ hexo d -g


