# 超级链接的美化

## 伪类
同一个标签，根据用户的某种状态不同，有不同的样式。这就叫做“伪类”
,伪类用冒号来表示。
a标签有4种伪类:

        a:link {
            color: red;
        }

        a:visited {
            color: green;
        }

        a:hover {
            color: blue;
        }
        a:active{
            color: black;
        }


`:link` 表示， 用户没有点击过这个链接的样式。 是英语“链接”的意思。
`:visited` 表示， 用户访问过了这个链接的样式。 是英语“访问过的”的意思。
`:hover` 表示， 用户鼠标悬停的时候链接的样式。 是英语“悬停”的意思。
`:active` 表示， 用户用鼠标点击这个链接，但是不松手，此刻的样式。 是英语“激活”的意思。

在css中，必须按照固定的顺序写：
`a:link 、a:visited 、a:hover 、a:active`如果不按照顺序，那么将失效。

