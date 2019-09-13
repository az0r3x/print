# print
Same as console.log from NodeJS but with time stamp (up to ms) and overwrite previous line.

### Install
`npm i @az0r3x/print`

### Usage
```Javascript
let print = require('@az0r3x/print');

print.timeStamp("OMG ITS A TIME STAMP");
print.timeStamp_ms("AND WITH MS!");
print.timeStamp("I CAN EVEN OVERWRITE THIS (IN 4 SECS)");
setTimeout(function(){
    print.inlineTimeStamp("NO WAY! ITS AWESOME!")
}, 4000)
```

### Parameters
+ **data:** Data to be shown (`string`, `array`, `object`, `number`)
+ **base (default is 10):** If `data` is a `number` type, then `base` defines in witch base the number must be show, e.g. binary (2), decimal (10), hexdecimal (16), etc.

### Methods
+ ***print.timeStamp(data[,base]):***
    + print.timeStamp("Hi!") ->                         [22:00:19] Hi!
    + print.timeStamp({"me":"ur age?", "you":20}) ->    [22:00:22] {"me":"ur age?", "you":20}
    + print.timeStamp(90) ->                            [22:00:24] 90
    + print.timeStamp(90, 16) ->                        [22:00:26] 5A
    + print.timeStamp(13, 2) ->                         [22:00:28] 1101
+ ***print.inlineTimeStamp(data[,base]): Overwrites the previous line***
    + print.inlineTimeStamp("Loading...") -> ~~[13:00:00] Loading...~~ [13:00:03] Complete!
    + print.inlineTimeStamp("Complete!") ------------------------------^
+ ***print.timeStamp_ms(data[,base]):***
    + print.timeStamp_ms("I'd like to be more precise!") ->  [10:20:09.023] I'd like to be more precise!
+ ***print.inlineTimeStamp_ms(data[,base]): Overwrites the previous line***
    + print.inlineTimeStamp_ms("Precise overwriting!") -> [11:30:49.001] Precise overwriting!

