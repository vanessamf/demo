# 浮动
## 实现效果 ##
?> 
<a class="btn btn-success" href="https://vanessamf.github.io/demos/fudong/index.html" role="button" target="_blank">
查看演示
</a>
### 具体过程一 ###

```html
<div class="arrow">
    <a href="javascript:void(0);">
        <i class="fa  fa-chevron-down "></i>
    </a>
</div>
```

```css
.arrow{
    position:absolute;
    top:50px;
    left:50%;
    
    -webkit-animation: bounce 2s infinite ease-in-out;
}
.arrow a:hover{
     color:#fdfc71
}
.arrow i{
    font-size:18px;
    border:1px solid ;
    border-radius:50%;
    padding:15px 15px;
}
@-webkit-keyframes bounce {
    0%, 20%, 60%, 100%  { -ms-transform: translateX(-50%) translateY(0); }
    0%, 20%, 60%, 100%  { -o-transform: translateX(-50%) translateY(0); }
    0%, 20%, 60%, 100%  { -moz-transform: translateX(-50%) translateY(0); }
    0%, 20%, 60%, 100%  { -webkit-transform: translateX(-50%) translateY(0); }
    40%  { -ms-transform:translateX(-50%)  translateY(-20px); }
    40%  { -o-transform: translateX(-50%) translateY(-20px); }
    40%  { -moz-transform:translateX(-50%)  translateY(-20px); }
    40%  { -webkit-transform:translateX(-50%)  translateY(-20px); }
    80%      { -ms-transform: translateX(-50%) translateY(-10px); }
    80%  { -o-transform:translateX(-50%)  translateY(-10px); }
    80%  { -moz-transform: translateX(-50%) translateY(-10px); }
    80%  { -webkit-transform: translateX(-50%) translateY(-10px); }
}
```


### 具体过程二 ###
```html
<div class="arrow2">
    <a href="javascript:void(0);">
        <i class="fa  fa-chevron-down "></i>
    </a>
</div>
```

```css
.arrow2{
    position:absolute;
    top:150px;
    left:50px;
    -webkit-animation: bounce1 2s infinite ease-in-out;
}
.arrow2 i{
    font-size:18px;
    border:1px solid ;
    border-radius:50%;
    padding:15px 15px;
}
@-webkit-keyframes bounce1 {
    0%, 50%, 100%  { -webkit-transform: translateY(0); }
    25%,75%  { -webkit-transform: translateY(-15px); }
}
```