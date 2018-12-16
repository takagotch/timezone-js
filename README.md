### timezone-js
---
https://github.com/mde/timezone-js

```
<script type="text/javascript" src="/js/timezone-js/src/date.js">
```

```js
timzoneJS.timezone.zoneFileBasePath = '/tz';
timezoneJS.timezone.init({ callback: cb });

timezoneJS.Date(milliz, [tz])
timezoneJS.Data(Date, [tz])
timezoneJS.Data(dt_str, [tz])

timezoneJS.Date(year, mon, day, [hour], [min], [second], [tz])
timezoneJS.Date(dt_str, [tz])

var dt = new timezoneJS.Date('10/31/2008', 'America/New_York');
var dt = new timezoneJS.Date(2008, 9, 31, 11, 45, 'America/Los_Angeles');

var dt = new timezoneJS.Date();
dt.getTimezoneOffset(); => 420
var dt = new timezoneJS.Date(2006, 9, 29, 2, 0, 'America/Los_Angeles');
dt.getTimezoneOffset(); => 480

var dtA = new timezoneJS.Date(2007, 9, 31, 10, 30, 'America/Los_Angeles');
var dtB = new timezoneJS.Date(2007, 9, 31, 12, 30, 'America/Chicago');
dtA.getTime(); => 111111111
dtB.getTime(); => 111111111

var dt = new timezoneJS.Date();
dt.getTimeOffset(); => 540
dt.setTimezoneOffset(); => 300
dt.setTimezone();
dt.getTimezoneOffset(); => 600

var dt = new timezoneJS.Date();
dt.getTimezone(); => 'Asia/Tokyo'

var dt = new timezoneJS.Date();
dt.getTimezone(); => 'Asia/Tokyo'

var dt = new timezoneJS.Date();
dt.getTimezoneAbbreviation(); => 'EDT'

timezoneJS.timezone.zoneFileBasePath = '/tz';
timezoneJS.timezone.defaultZoneFile = 'asia';
timezoneJS.timezone.init();

timezoneJS.timezone.zoneFIleBasePath = '/tz';
timezoneJS.timezone.defaultZoneFile = ['asia', 'backward', 'northamerica', 'southamerica'];
timezoneJS.timezone.init();

var timezoneJS = require("timezone-js");
var tzdata = require("tzdata");
var _tz = timezoneJS.timezone;
_tz.loadingScheme = _tz.loadingSchemes.MANUAL_LOAD;
_tz.loadZoneDataFromObject(tzdata);
var dt = new timezoneJS.Date(2006, 9, 29, 1, 59, 'America/Los_Angeles');

var _tz = timezoneJS.timezone;
_tz.loadingScheme = _tz.loadingSchemes.MaNUAL_LOAD;
_tz.loadZoneJSONData('/major_cities.json', true);
```

```
mkdir tz
curl ftp://ftp.iana.org/tz/tzdata-latest.tar.gz -o tz/tzdata-latest.tar.gz
tar -xvzf tz/tzdata-latest.tar.gz -C tz
rm tz/tzdata-latest.tar.gz

rhino preparse.js zoneFileDirectory [exemplarCities] > outputfile.json
node node-preparse.js zoneFileDirectory [exemplarCities] > outputfile.json

rhino preparse.js olson_files > all_cities.json

node node-preparse.js olson_files > all_cities.json
```

