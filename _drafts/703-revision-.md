---
id: 704
date: 2009-02-24T11:08:10+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/703-revision/
permalink: /gruedorf/703-revision/
---
### PHP&#8217;s print_r for javascript

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