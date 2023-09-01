```js
var app_footer = document.getElementsByClassName('app-footer')[0];

var content = document.createElement("div");
content.innerHTML = `<a target="_blank" href="https://beian.miit.gov.cn/" style="text-decoration:none;">
  <p style="display: inline;color:#939393;">
    备案号：湘ICP备2022002232号-2
  </p>
  <img title="备案" src="/备案.png" style="display: inline;">
  <p style="display: inline;color:#939393;">
    湘公网安备 43010302001628号
  </p>
</a>`;

app_footer.appendChild(content);
```

## HTML 参考

```html
<div>
  <a target="_blank" href="https://beian.miit.gov.cn/" style="text-decoration:none;">
    <p style="display: inline;color:#939393;">
      备案号：湘ICP备2022002232号-2
    </p>
    <img title="备案" src="/备案.png" style="display: inline;">
    <p style="display: inline;color:#939393;">
      湘公网安备 43010302001628号
    </p>
  </a>
</div>
```

