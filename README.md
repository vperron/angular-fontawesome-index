angular-fontawesome-index
=========================

**A tiny service to map fontawesome class names to their unicode counterparts**

---

Ever needed to draw [fontawesome][Font Awesome] icons over a map, for instance ? 

Use this handy service to provide you the necessary unicode code points.

    angular.module('myApp', ['angular-fontawesome-index', ...])

    angular.module('myApp').factory('FooService', ['FontAwesomeIndex', (FontAwesomeIndex) ->
      
      icon_unicode = FontAwesomeIndex['fa-mobile']

    )



Secret
------

Generated with my lovely vim from font-awesome.css:

    // replace every doubled icon class by two CSS clauses. repeat until pattern is not found anymore.
    %s/\.\(.*\):before,\(\_.\{-} {\)\(\_.\{-}\)\n}/.\1:before  {\3\r}\2\3\r}/gI

    // transform the css classes into a dictionary-like list
    %s/\.\(.*\):before\_.\{-}"\(\\.*\)";\n}/'\1': '\2'

    // change the codes to be Javascript unicode characters
    %s/'\\f/'\\uf

    // add end-of-line commas
    %s/'\n/',\r/gI



Licence
-------

MIT
