# Centrarium [![Circle CI](https://circleci.com/gh/bencentra/centrarium/tree/master.svg?style=svg)](https://circleci.com/gh/bencentra/centrarium/tree/master)

------

Jekyll 웹 사이트 또한 블로그를 위한 간단하면서도 고급스러운 테마.
스타일이나 브랜드에 맞게 사용자 정의 가능

다음과 같은 라이브러리로 구축:

- Bourbon
- Neat
- Bitters
- Refills
- Font Awesome
- HighlightJS
- Lightbox

## Features

------

이 테마는 다음을 포함한 여러 기능과 함께 제공

- Easily customizable fonts and colors
- Cover images for your homepages and blog posts
- Pagination(쪽수 매기기) enabled by default
- Archiving of posts by categories and tags
- Syntax highlighting for code snippers
- Disqus integration for post comments
  - Disqus는 소셜 댓글 서비스. Social Media를 활용한 댓글 시스템으로 facebook, twitter와 같은 소셜 네트워크와 연동해서 댓글을 달 수 있게 만들어 주는 서비스
- Lightbox for viewing full-screen photos and albums
- Google Analytics with custom page name tracking
- Social media integration (Twitter, Facebook, LinkedIn, Github, and more)

## Installation

------

Jekyll을 처음 다룬다면 이 저장소를 자신의 사이트를 위한 시작점으로 사용 가능.
이 프로젝트를 다운로드하고 모든 파일을 프로젝트에 추가.
`posts/` 디렉토리에 블로그 게시물을 추가하고 적절한 Jekyll 머리말 페이지를 만들어야 한다.
(예는 `posts.html` 참조)

이미 Jekyll을 사이트에 적용하고 있다면, 다음과 같은 단계를 따른다:

1. `_includes`,`_layouts` 및 `_sass` 디렉토리의 파일을 이 프로젝트의 파일로 변경.
2. `index.html`을 이 프로젝트의 파일로 변경하고. `posts.html`파일도 복사.
3. 이 프로젝트의 `_confit.yml` 내용을 자신의 것으로 복사하고 필요한 정보 업데이트.

Jekyll과 다른 dependecies들의 설치도 잊지말 것.

```bash
# cd into project directory
cd centrarium
# install Bundler if you don't have it already
gem install bundler
# install jekyll, jekyll-archives, jekyll-sitemap, and jekyll-paginate
bundle install
```

## Stackbit Deploy

------

이 테마는 Stackbit으로 가져올 수 있다. 이 테마는 Netlify에 배포할 수 있으며 Forestry, NetlifyCMS, DatoCMS 또는 Contentful을 포함한 모든 headlessCMS를 연결 할 수 있다.

[![Create with Stackbit](https://assets.stackbit.com/badge/create-with-stackbit.svg)](https://app.stackbit.com/create?theme=https://github.com/bencentra/centrarium)

## Updating Header and Footer Links

------

header와 footer의 링크가 자동 생성된다. `category: page`로 표시된 모든 파일에 대한 링크가 작성되고, 제목이 있고 사용자 정의 `main_nav` front-matter 변수가 `true`로 설정된 파일들에 적용된다. `_layouts/nav_links.html`에서 링크 생성 규칙을 수정할 수 있다.

## Updating Styles

------

테마의 CSS를 변경하려면 `_sass/` 디렉토리에서 다음 파일을 변경한다:

- `base/_variables.scss`: 기본 글꼴 크기, 글꼴 군, 색상 등으르 포함하여 프로젝트 전체에서 사용되는 공통 값이다. 
- `base/_typography.scss`: 사이트의 기본 typography 값 (demo는 `typography.html`참조)

* `_layout.scss`: 테마 레이아웃 및 디자인의 기본 스타일이다.

### Important Variables

다음은 테마를 원하는 대로 사용자 정의하기 위해 조정할 수 있는 `base/_variables.scss`의 중요한 변수이다:

* `$base-font-family`: 본문 텍스트의 글꼴 계열. 새 글꼴은 모두`@import`
* `$heading-font-family`: 헤더의 글꼴 패밀리. 새 글꼴은 모두`@import`
* `$base-font-size`: 기본 글꼴 크기. 기본값은 Bourbon에서 $em-base (`bourbon/settings/_px-to-em.scss`).
* `$base-font-color`: 본문 텍스트의 색.
* `$action-color`: 본문 텍스트의 링크 색.
* `$highlight-color`: footer와 page headers의 색상 (when no cover image provided).

## Configuration

------

모든 configuration options은 `_config.yml`에서 수정한다.

### Site Settings

* __title:__ 사이트의 타이틀. navigation menu, `index.html` header와 footer에 표시.
* __subtitle:__ 사이트의 부제. `index.html` header에 표시.
* __email:__ 메일 주소, footer의 Contact info에 표시.
* __name:__ 이름. _Currently unused._
* __description:__ 사이트 설명. 검색 엔진 결과에 사용되며, footer에 표시.
* __baseurl:__ 사이트의 subpath (e.g. /blog/).
* __url:__ 사이트의 기본 호스트 이름 및 프로토콜.
* __cover:__ 사이트의 커버 이미지에 대한 상대 경로.
* __logo:__ 사이트의 로고에 대한 상대 경로. 제공된 경우 제목 대신 탐색 메뉴에서 사용.

### Build Settings

* __markdown:__ 디폴트는 kramdown
* __inter_post_navigation:__ 각 게시물의 다음 게시물과 이전 게시물에 대한 링크를 렌더링할지 여부를 나타낸다.

### Pagination settings

See the documentation for [jekyll-paginate-v2](https://github.com/sverrirs/jekyll-paginate-v2/blob/master/README-GENERATOR.md#site-configuration) for more details.

### Archive Settings

이 테마에는 분류된 복합 아카이브 (see `posts.html`)가 포함되어 있지만, [jekyll-archives][archives] 덕분에 추가 아카이브 생성을 활성화할 수 있다. 카테고리 및 태크 아카이브 페이즈에 대한 지원이 포함되지만 연도, 월 및 일 동안 자신의 아카이브 페이지를 추가할 수도 있다. 

Archive 설정을 변경하려면 `_config.yml`의  __jekyll-archives__ 섹션을 참고 :

```yml
jekyll-archives:
  enabled:
    - categories
    - tags
  layout: 'archive'
  permalinks:
    category: '/category/:name/'
    tag: '/tag/:name/'
```

Archive를 완전히 비활성화하려면  __jekyll-archives__ 섹션을 제거하고 AND __gems__ list에서 제거.

__NOTE:__ Jekyll Archive gem은 Github 페이지에 포함되어 있지 않다. 사이트를 Github 페이지에 배포하려는 경우 보관 기능을 사용하지 않도록 설정한다. [Here is a guide](http://ixti.net/software/2013/01/28/using-jekyll-plugins-on-github-pages.html) 가이드에는 `jekyll archive` gem을 GitHub pages에서 사용할 수 있는 방법을 설명한다. 일반적인 요지는 Jekyll 사이트를 locally하게 컴파일하고 그 사이트를 Github에 게시하는 것이다.

사이트맵 또한 [jekyll-sitemap][sitemap]를 통해 생성한다.

### Syntax Highlighting Settings

게시물 내부에서는 `{% highlight <language> %}` Liquid tag를 사용하여 구문 강조 표시를 활성화할 수 있다. 예시:

```
{% highlight javascript %}
function demo(string, times) {
  for (var i = 0; i < times; i++) {
    console.log(string);
  }
}
demo("hello, world!", 10);
{% endhighlight %}
```

 `_config.yml` 안에서 [HighlightJS theme][highlightjs_theme] 를 변경할 수 있다.:

```yml
highlightjs_theme: "monokai_sublime"
```

### Disqus Settings

[Disqus][disqus] 하나의 config option으로 disqus comment를 사용할 수 있다:

* __disqus_shortname:__ 사용자의 Disqus username. 속성을 설정하면 Disqus 설명이 블로그 게시물에 포함된다.

특정 페이지에 대해서만 Disqus르르 비활성화하려면 페이지의 앞부분에 __disqus_disabled: true__ 를 추가

### Google Analytics Settings

[Google Analytics][ga] pageview tracking을 활성화 할 수 있다.:

* __ga_tracking_id__: 웹 사이트의 tracking ID. Google Analytics 대시보드에서 찾을 수 있다. 속성을 설정하면 각 페이지의 바닥글에 Google Analytics가 추가된다.

### Social Settings

개인 소셜 네트워크 설정이 social sharing option과 결합된다. `_config.yml`의 __social__ 섹션에 포함할 각 네트워크에 대한 항목을 포함한다. 예시:

```yml
social:
  - name: Twitter                         # Name of the service
    icon: twitter                         # Font Awesome icon to use (minus fa- prefix)
    username: TheBenCentra                # (User) Name to display in the footer link
    url: https://twitter.com/TheBenCentra # URL of your profile (leave blank to not display in footer)
    desc: Follow me on Twitter            # Description to display as link title, etc
    share: true                           # Include in the "Share" section of posts
```

### Social Protocols

Open Graph Protocol 또는 Twitter Card 메타데이터를 사용하여 사람들이 트위터 또는 Facebook에서 사이트를 공유할 때 사용되는 이미지와 텍스트를 자동으로 설정할 수 있습니다. 이것은 약간의 설정이 필요하지만 충분히 가치가 있다. 관련 필드는 `_config.yml` 파일의 끝에 있다.

또한 소스가 열려 있는 경우 사이트가 호스트되는 위치를 나타내는 다른 프로토콜인 오픈 소스 프로토콜도 있습니다. 이렇게 하면 관심이 있거나 문제가 있는 경우 코드를 보다 쉽게 볼 수 있습니다. 자세한 내용은  http://osprotocol.com를 참조.

### Category Descriptions

포스트 카테고리에 대한 설명과 함께 `posts.html` 아카이브 페이지를 향상시킬 수 있다.`_config.yml`의 __descriptions__ 참조 :

```yml
# Category descriptions (for archive pages)
descriptions:
  - cat: jekyll
    desc: "Posts describing Jekyll setup techniques."
```

### Custom Page-Specific Javascript

최상위 `/js` 디렉토리에 페이지별 javascript 파일을 추가하고  __custom_js__ 페이지의 config 파일에 파일 이름을 포함하여 페이지별 javascript 파일을 추가할 수 있다:

```yml
# Custom js (for individual pages)
---
layout: post
title:  "Dummy Post"
date:   2015-04-18 08:43:59
author: Ben Centra
categories: Dummy
custom_js:
- Popmotion
- Vue
---
```

`/js/`디렉토리에는 다음과 같은 파일이 포함된다:

```bash
$ ls js/
Popmotion.js Vue.js
```

## Contributing

------

Want to help make this theme even better? Contributions from the community are welcome!

Please follow these steps:

1. Fork/clone this repository.
2. Develop (and test!) your changes.
3. Open a pull request on GitHub. A description and/or screenshot of changes would be appreciated!
4. I ([Ben Centra](https://github.com/bencentra)) will review and merge the pull request.

## License

MIT. See [LICENSE.MD](https://github.com/bencentra/centrarium/blob/master/LICENSE.md).

[bencentra]: http://bencentra.com
[bourbon]: http://bourbon.io/
[neat]: http://neat.bourbon.io/
[bitters]: http://bitters.bourbon.io/
[refills]: http://refills.bourbon.io/
[fontawesome]: http://fortawesome.github.io/Font-Awesome/
[highlightjs]: https://highlightjs.org/
[highlightjs_theme]: https://highlightjs.org/static/demo/
[lightbox]: http://lokeshdhakar.com/projects/lightbox2/
[cover]: https://www.flickr.com/photos/79666107@N00/3796678503/in/photolist-6MuYfc-61Rtft-8XzPmY-a6Cozm-54eSMs-6oMJmk-aepZQq-9YkPHp-fiAEGE-dVP4Z5-oxPyJP-atKUFJ-9YHWA5-9YF2f2-9YF2gR-9YHVGN-9YHVvs-qZYYQ6-4JqP2i-a2peGy-9YHVUm-9YHVF7-9YHVCL-9YF3NK-cYteMo-aiPmb9-69dtAi-9YF21x-4aWpmn-7SLiUL-77pqVX-8vXbYv-4HGDSH-a2h5P1-8LsZrQ-9aj1ez-auPZ7q-9YHVMd-9YF2bi-9YF23D-8LpWpn-9an6KL-9YHVZL-dqZ3Cz-2GuvnX-9YHWUo-9YHVWd-p5Roh5-i1zTbv-6sYrUT
[disqus]: https://disqus.com/
[ga]: http://www.google.com/analytics/
[archives]: https://github.com/jekyll/jekyll-archives
[sitemap]: https://github.com/jekyll/jekyll-sitemap