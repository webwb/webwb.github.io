---
layout: post
comments: true
categories: life
published: false
title: Responsive
---
## Damit padding zur Breite der Box gezählt wird

* {
  box-sizing: border-box;
}

## Media Queries setzen

@media only screen 
and (max-width : 420px) {
  .col {
    width: 50%;
  }
}
