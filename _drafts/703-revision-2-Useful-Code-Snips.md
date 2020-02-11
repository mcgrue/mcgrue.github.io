---
id: 705
title: Useful Code Snips
date: 2009-02-24T11:08:34+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/703-revision-2/
permalink: /gruedorf/703-revision-2/
---
### PHP&#8217;s print_r for javascript

Googled from <a href=http://www.brandnewbox.co.uk/articles/details/a\_print\_r\_equivalent\_for\_javascript/>http://www.brandnewbox.co.uk/articles/details/a\_print\_r\_equivalent\_for\_javascript/</a>

<pre>unction print_r(theObj){
  if(theObj.constructor == Array ||
     theObj.constructor == Object){
    document.write("

<ul>
  ")
      for(var p in theObj){
        if(theObj[p].constructor == Array||
           theObj[p].constructor == Object){
  document.write("
  
  <li>
    ["+p+"] => "+typeof(theObj)+"
  </li>");
          document.write("
  
  <ul>
    ")
            print_r(theObj[p]);
            document.write("
  </ul>")
        } else {
  document.write("
  
  <li>
    ["+p+"] => "+theObj[p]+"
  </li>");
        }
      }
      document.write("
</ul>")
  }
}
</pre>