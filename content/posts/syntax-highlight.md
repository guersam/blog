+++
title = "문법 강조가 잘 되는지 알아봅시다"
slug = "trying-syntax-highlight"
date = 2018-02-18T15:12:51+09:00
tags = ["hugo"]
categories = []
+++

가끔 코드도 올려볼까 합니다. 신나겠지요.

본문 초반에 소스코드가 들어가면 내용이 목록에도 다짜고짜 표시되어 보기 좋지 않으니 코드 블록 전에 &lt;!--more--&gt;를 직접 붙여 주어야 합니다.

<!--more-->

원본 마크다운 파일에는 위 문단과 이 문단 사이에 &lt;!--more--&gt;가 들어있지만 휴고가 알아서 잘라먹고 html파일에는 보여주지 않습니다. 어쨌든 소스코드를 넣어 볼까요,

```scala
$ amm
Loading...
Welcome to the Ammonite Repl 1.0.1
(Scala 2.12.3 Java 1.8.0_151)
If you like Ammonite, please support our development at www.patreon.com/lihaoyi

@ import $ivy.`org.typelevel::cats-core:1.0.1` 
import $ivy.$                               

@ import cats.implicits._ 
import cats.implicits._

@ val ys = (1 to 10).toList.traverse(_.show.some) 
ys: Option[List[String]] = Some(
  List("1", "2", "3", "4", "5", "6", "7", "8", "9", "10")
)
```

휴고가 **\`\`\`scala** 같은 코드 블록에도 문법 강조를 적용하게 하려면 `config.toml`에서 `pygmentsCodeFences = true` 설정을 켜야 했습니다.
