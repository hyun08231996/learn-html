# HTML & CSS



## ✅ Shortcuts

- `!` + `tab` : html 기본 템플릿 자동 생성
- `opt` + `shift` + `⬇︎` : 한줄 복사
- `tag 이름` + `tab` : tag 자동 완성 (예. `p` + `tab` ⇒ `<p></p>` )
- `lorem30` : lorem ipsum 자동 생성 (숫자 만큼 생성됨)
- `div#id` + `tab` ⇒ `<div id=”id”></div>`
- `div.class` + `tab` ⇒ `<div class=”class”></div>`
- `input:checkbox` + `tab` ⇒ `<input type=”checkbox”>`
- [emmet shortcut list](https://docs.emmet.io/cheat-sheet/)

## ✅ HTML : Good to know

- `h1` 태그는 페이지 당 주로 한번만 사용, `h1` 태그에는 주로 로고 삽입(예. 네이버)
- 사이트의 주 목적은 수익 창출. 수익이 많으려면 유저가 많아야 하는데,검색 노출 잘되려면, `html` 코드가 잘 짜여져 (최적화 되어) 있어야 한다 (갖춰진 태그들을 잘 활용) → [SEO (Search Engine Optimization)](https://developers.google.com/search/docs/fundamentals/seo-starter-guide#:~:text=SEO%E2%80%94short%20for%20search%20engine,site%20through%20a%20search%20engine.)
- Convention : custom attribute 만들려면 앞에 data prefix를 붙이자! (예. `data-test=”test”`)
- basic tags :
    - `<abbr>` : 줄임말
    - `<figure>` : 주로 이미지가 들어가고 이미지를 설명하는 `<figcaption>`도 함께 활용 (`figcaption` 사용하면 `img` 요소의 `alt` attribute 불필요)
- semantic tags :
    - `<header>` : 페이지 가장 상단
    - `<nav>` : 주로 `<header>` 안에 있고, `ul>li` 태그가 포함됨
    - `<section>` : `h1`은 들어가면 안되고, 하나 이상의 `h` 태그가 들어가야 한다
    - `<main>` : 페이지당 1번만 사용해야 한다 (`header` & `footer` 제외한 모든 요소는 `main` 안에 들어감)
    - `<aside>` : 사이드에 주로 배치함 (예. 광고 배너)
    - `<article>` : 독립적으로 배포 가능하거나 재사용할 수 있는 콘텐츠를 묶는 영역
    - `<footer>` : 페이지 가장 하단
- form tags :
    - `<input>` 태그는 주로 `<label>` 태그와 함께 사용
    - `<button></button>` 은 `type=”submit”` attribute가 자동으로 들어가있어서, 제출할 게 아니라면 `<button type=”button”></button>`을 사용해야함 (단축키 : `btn:b` + `tab`)
- Inline & Block
    - `<img>` 와 `<input>` 태그는 inline 이지만 width, height 등 적용 가능
- WAI-ARIA (Web Accessibility Initiative's Accessible Rich Internet Applications) : 스크린리더가 브라우저를 읽을 때 각 요소가 어떤 역할을 하는지 무슨 의미로 존재하는지 알 수 있도록 하기 위해 만들어진 기술
    - `aria-role`, `aria-label`, `aria-describedby` 등의 속성이 있음
    - `tabindex="0"` : Makes an element focusable within sequential keyboard navigation
        - `tabindex` 는 보통 `0` 또는 `-1` 값만 사용
    

## ✅ CSS : Good to know

- 태그 상속
    - 부모가 자식에게 `font style`(서체, 크기, 자간, 행간 등)을 물려주고, 자식은 부모에게 `height` 값을 물려준다
        - 따라서, `height` 설정은 부모에게 직접하지 않고, 자식에게만 설정하고 부모의 `height` 은 자동으로 자식의 `height`의 합계를 물려받게 한다 (예. 자식1 height : 200px + 자식2 height : 200px = 부모 height : 400px)
- inline 방식은 사용하지 않는 게 좋음 : 코드 복잡해지면 유지보수 어려워짐
    - 외부 방식을 사용하자!!
- css selector 우선순위
    - 일반 태그 (예. `p`, `div`) : 1점
    - 클래스 (예. `.box`) 또는 속성 (예. `[name=”box”]`) : 10점
    - 아이디 (예 `#box`) : 100점
    - 점수 조합 :
        - 앞에 일반 태그를 붙이면 1점 플러스됨
            - 예. `p.box` 또는 `p[name=”box”]` : 11점
        - 클래스 여러개 연속적으로 조합
            - 예. `.box-1.box-2.box-3.box-4` : 40점
        - 부모 자식 조합
            - 예. `#color_box .bg` : 110점
    - css 파일에서 selector에 hover 해보면 확인 가능
        
        ![image](./img/image.png)