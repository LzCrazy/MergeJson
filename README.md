# MergeJson


```
     (function($)
            {$.concat||$.extend
            ({concat:function(){
                return Array.prototype.concat.apply([],arguments);
            }})
                })(jQuery);
```