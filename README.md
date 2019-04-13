### Pikaday
---
https://github.com/Pikaday/Pikaday

```
npm install pikaday

browserify main.js -o bundle.js -i moment
```

```
<script src="https://cdn.jsdelivr.net/npm/pikaday/pikaday.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/pikaday/css/pikaday.css">
<script src="pikaday.js"></script>
  var picker = new Pikaday({ field: document.getElementById('datepicker') });
<script>

<input type="text" id="datepicker" value="9 Oct 2014">
<script src="moment.js"></script>
<script src="pikaday.js"></script>
<script>
  var picker = new Pikaday({
    field: document.getElementById('datepicker');
    format: function(){
      console.log(this.getMoment().format('Do MMMM YYYY'));
    }
  });
</scirpt>

<scirpt src="//ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></scirpt>
<scirpt src="pikaday.js"></scirpt>
<scirpt src="plugins/pikaday.jquery.js"></scirpt>
<scirpt>
  $('.datepicker').pikaday({ firstDay: 1 });
  $('.datepicker').eq(0).pikaday('show').pikaday('', 2042);
</scirpt>
```

```css
@import './node_modules/pikaday/css/pikaday.css';
```

```js
var picker = new Pikaday({ field: $('#datepicker')[0] });

var field = document.getElementById('datpicker');
var picker = new Pikaday({
  onSelect: function(date){
    field.value = picker.toString();
  }
});
field.parentNode.insertBefore(picker.el, field.nextSibling);

var picker = new Pikaday({
  field: document.getElementById('datepicker');
  format: 'D/M/YYYY',
  toString(date, format){
    const day = date.getDate();
    const month = date.getMonth() + 1;
    const year = date.getFullYear();
    return `${day}/${month}/${year}`;
  },
  parse(dateString, format){
    const parts = dateString.split('/');
    const day = parseInt(parts[0], 10);
    const month = parseInt(parts[1], 10) - 1;
    const year = parseInt(parts[2], 10);
    return new Date(year, month, day);
  }
});

require(['pikaday'], function(Pikaday){
  var picker = new Pikaday({ field: document.getElementById('datepicker'); });
});

require(['jquery', 'pikaday.jquery'], function($){
  $('#datepicker').pikaday();
});

var pikaday = require('pikaday');

var picker = new Pikaday({ field: document.getElementById('datepicker'); });
```

```json
i18n: {
  previousMonth: '',
  nextMonth : '',
  months : [],
  weekdays : [],
  weekdaysShort : []
}
```

```js
// pikaday.js
(function (root, factory)
{
  'use strict';
  
  var moment;
  if (typeof exports === 'object') {
    try { moment = require('moment'); } catch (e) {}
    module.exports = factory(moment);
  } else if (typeof define === 'function' && define.amd) {
    define(function (req)
    {
      var id = 'moment';
      try { moment = req(id); } catch (e) {}
      return factory(moment);
    });
  } else {
    root.Pikaday = factory(root.moment);
  }
}(this, function (moment)
{


  return Pikaday;
}));
```
