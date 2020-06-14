
### accounts
- you gotta have a WeChat account
- and an AppID (you COULD use a *test* AppID though)

### download the developer tool
- modified version of VS Code
- with an emulator
- with special features designed for WeChat mini program

### basics about configuration
- there're three types of config out there
    1. sitemap (/sitemap.json)
    2. devtools config ([/project.config.json](https://developers.weixin.qq.com/miniprogram/dev/devtools/projectconfig.html))
        - as the doc states, it's kinda like a mix of `settings.json` <small>(VS Code)</small> and `package.json` <small>(node)</small>
    3. config of actual pages
        - [/app.json](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/app.html)
        - [/pages/PAGE\_NAME/PAGE\_NAME.json](https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/page.html) <small>(override objects under `window` object)</small>
- about some pre-existed config in app.json
    - `pages`: tell WeChat where your pages are (sub-folders)
    - `window`: configure global styles/texts (top bgcolor etc.)
        - you could override it in every json files under each pages 

### random config I've written
- `tabBar`
    ```javascript
    "tabBar": {
        "list": [
          {
            "pagePath": "pages/index/index",
            "text": "首页",
            "iconPath": "images/icon-home.png",
            "selectedIconPath": "images/icon-home-hl.png"
          },
          {
            "pagePath": "pages/logs/logs",
            "text": "日志",
            "iconPath": "images/icon-log.png",
            "selectedIconPath": "images/icon-log-hl.png"
          }
    ]
    ```

### Conventions you need to know
- **Comments** and **trailing commas** are not allowed inside `.json` files.

### Files under `/pages/`
- `.js`
    - Just some normal `.js` files, only with different APIs
- `.json`
    - Override some options stated in the `/app.js`, customization basically
- `.wxml`, `.wxss`
    - Modified version of `.html` and `.css`
    - `.wxml`
        - You could view it as *Vue-like syntax sugars* plus *slightly different tag names*
    - `.wxss`
        - Mostly the same as *CSS*, but with .. *limitaions*
- BONUS
    - There's also a [`.wxs` file](https://developers.weixin.qq.com/miniprogram/dev/reference/wxs/) <sup>([简介](https://segmentfault.com/a/1190000015067395))</sup>, it has JavaScript-like syntax.
    - **You don't have to use it**.