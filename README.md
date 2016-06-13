# sass-fail-demo
a demo for https://github.com/brunch/brunch/issues/1402

```sh
npm start
# should hang without returning an error, will trying to burn your CPU
```

To get the missing libsass error:
```sh
node_modules/node-sass/bin/node-sass app/failing_import.scss
```
Should return:
```json
{
  "formatted": "Error: File to import not found or unreadable: ../some/inexisting/file
       Parent style sheet: /home/maxlath/Bidouille/sass-fail-demo/app/failing_import.scss
        on line 1 of app/failing_import.scss
>> @import '../some/inexisting/file'
   ^
",
  "message": "File to import not found or unreadable: ../some/inexisting/file
Parent style sheet: /home/maxlath/Bidouille/sass-fail-demo/app/failing_import.scss",
  "column": 1,
  "line": 1,
  "file": "/home/maxlath/Bidouille/sass-fail-demo/app/failing_import.scss",
  "status": 1
}
```
