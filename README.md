```


<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head id="Head1"><title>
	枚举选择
</title>
    <script src="scripts/jquery-1.4.4.min.js" type="text/javascript"></script>
    <script src="scripts/jquery.ztree.core-3.5.min.js" type="text/javascript"></script>
    <link href="Styles/zTreeStyle.css" rel="stylesheet" type="text/css" />
    <style type="text/css">
	body{margin:0;}
        .HeadToolBack
        {
            padding-top: 2px;
            padding-right: 2px;
            padding-bottom: 2px;
            padding-left: 2px;
            border-top: 0px solid #a9bfd3;
            border-right: 0px solid #a9bf3;
            border-bottom: 1px solid #a9bfd3;
            border-left: 0px solid #a9bf3;
            line-height: 20px;
            background-image: url("image/toolbar/bg.gif");
            background-attachment: scroll;
            background-repeat: repeat-x;
            background-color: rgb(208,222,240);
        }
        .btnToolSmall
        {
            border-style: none;
            font-size: 12px;
            background-image: url('image/frame/txt4.gif');
            vertical-align: middle;
            cursor: hand;
            padding-top: 1px;
            width: 70px;
            background-repeat: no-repeat;
            height: 21px;
            background-color: transparent;
            text-align: center;
        }
    </style>
    <script type="text/javascript">
		<!--
        var setting = {
            data: {
                simpleData: {
                    enable:true,
                    idKey: "id",
			        pIdKey: "pId",
			        rootPId: "ROOT"
                }
            },
            async: {
                enable: true,
                autoParam: ["value=id","group"],
                type: "post",
                url: "EnumHandler.ashx"//,
                //dataFilter: filter
            }
        };
        var zNodes = [{"id":2,"group":"1","value":"0","name":"行政区划","isParent":true},{"id":1,"group":"1","value":"","name":"中国","pId":2,"isParent":false},{"id":4545,"group":"1","value":"11","name":"北京市","pId":2,"isParent":true},{"id":4624,"group":"1","value":"12","name":"天津市","pId":2,"isParent":true},{"id":4701,"group":"1","value":"13","name":"河北省","pId":2,"isParent":true},{"id":5450,"group":"1","value":"14","name":"山西省","pId":2,"isParent":true},{"id":5991,"group":"1","value":"15","name":"内蒙古","pId":2,"isParent":true},{"id":6354,"group":"1","value":"21","name":"辽宁省","pId":2,"isParent":true},{"id":6597,"group":"1","value":"22","name":"吉林省","pId":2,"isParent":true},{"id":76,"group":"1","value":"23","name":"黑龙江省","pId":2,"isParent":true},{"id":378,"group":"1","value":"31","name":"上海市","pId":2,"isParent":true},{"id":419,"group":"1","value":"32","name":"江苏省","pId":2,"isParent":true},{"id":671,"group":"1","value":"33","name":"浙江省","pId":2,"isParent":true},{"id":885,"group":"1","value":"34","name":"安徽省","pId":2,"isParent":true},{"id":1147,"group":"1","value":"35","name":"福建省","pId":2,"isParent":true},{"id":1345,"group":"1","value":"36","name":"江西省","pId":2,"isParent":true},{"id":1577,"group":"1","value":"37","name":"山东省","pId":2,"isParent":true},{"id":1909,"group":"1","value":"41","name":"河南省","pId":2,"isParent":true},{"id":2279,"group":"1","value":"42","name":"湖北省","pId":2,"isParent":true},{"id":2522,"group":"1","value":"43","name":"湖南省","pId":2,"isParent":true},{"id":2807,"group":"1","value":"44","name":"广东省","pId":2,"isParent":true},{"id":3109,"group":"1","value":"45","name":"广西壮族","pId":2,"isParent":true},{"id":3370,"group":"1","value":"46","name":"海南省","pId":2,"isParent":true},{"id":3424,"group":"1","value":"50","name":"重庆市","pId":2,"isParent":true},{"id":3507,"group":"1","value":"51","name":"四川省","pId":2,"isParent":true},{"id":3927,"group":"1","value":"52","name":"贵州省","pId":2,"isParent":true},{"id":4119,"group":"1","value":"53","name":"云南省","pId":2,"isParent":true},{"id":4410,"group":"1","value":"54","name":"西藏","pId":2,"isParent":true},{"id":4586,"group":"1","value":"61","name":"陕西省","pId":2,"isParent":true},{"id":5079,"group":"1","value":"62","name":"甘肃省","pId":2,"isParent":true},{"id":5509,"group":"1","value":"63","name":"青海省","pId":2,"isParent":true},{"id":5701,"group":"1","value":"64","name":"宁夏回族","pId":2,"isParent":true},{"id":5818,"group":"1","value":"65","name":"新疆维吾尔","pId":2,"isParent":true},{"id":6670,"group":"1","value":"66","name":"新疆建设兵团","pId":2,"isParent":true}];
        function getParam (paramName, urlString) {
            var paramValue = "", isFound = false, url = urlString;
            if (!url) url = window.location.search;
            if (url.indexOf("?") == 0 && url.indexOf("=") > 1) {
                var arrSource = unescape(url).substring(1, url.length).split("&");
                var i = 0;
                while (i < arrSource.length && !isFound) {
                    if (arrSource[i].indexOf("=") > 0) {
                        if (arrSource[i].split("=")[0].toLowerCase() == paramName.toLowerCase()) {
                            paramValue = arrSource[i].split("=")[1];
                            isFound = true;
                        }
                    }
                    i++;
                }
            }
            return paramValue;
        }
        $(document).ready(function () {
            $.fn.zTree.init($("#treeDemo"), setting, zNodes);
            var treeObj = $.fn.zTree.getZTreeObj("treeDemo");
            var nodes = treeObj.getNodes();
            treeObj.expandNode(nodes[0], true, false, true);
        });

         function goBack(){
            var treeObj = $.fn.zTree.getZTreeObj("treeDemo");
            var nodes = treeObj.getSelectedNodes();
            
            if(nodes.length==0)
            {
                window.close();
                return;
            }
            else{
                var obj=new Object(); 
                obj.text=nodes[0].name;
                if(nodes[0].pId == 'ROOT' && nodes[0].group !='1'){
                    obj.value='';
                }else{
                    obj.value=nodes[0].value;
                }
                window.returnValue=obj;
                var parent = window.dialogArguments || window.opener;//window.opener || window.parent;
               
                if(parent){ 
                    if(parent.postMessage) {
                        var msg = {source:'popenum',target:getParam('n'),data:obj };
                        parent.returnValue = msg;
                        parent.postMessage(msg,'*');
                    }
                }
                window.close();
            }
         }
 
        function btnClose()
        {
            window.close();
        }
		//-->
    </script>
</head>
<body>
    <form method="post" action="EnumSelectEx.aspx?group=1&amp;n=queryGroupEnumItem_227" id="form1">
<div class="aspNetHidden">
<input type="hidden" name="__VIEWSTATE" id="__VIEWSTATE" value="/wEPDwULLTExOTI5NTg5NjlkZEY1DxQxx0a0NcH33sVwD/N50JCtUZ8yjTZI6sI75to5" />
</div>

<div class="aspNetHidden">

	<input type="hidden" name="__VIEWSTATEGENERATOR" id="__VIEWSTATEGENERATOR" value="1CD7EBEC" />
</div>
    <table id="Table1" cellspacing="0" cellpadding="0" width="100%" border="0">
        <tr>
            <td class="HeadToolBack">
                <table cellspacing="0" cellpadding="0" width="100%" border="0">
                    <tr>
                        <td>
                            请选择：
                        </td>
                        <td align="left">
                        </td>
                        <td align="right">
                            <input type="button" class="btnToolSmall" value="确 定" onclick="goBack()" />
                            <input type="button" class="btnToolSmall" value="取 消" onclick="btnClose()" />&nbsp;&nbsp;
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
        <tr>
            <td>
           <div style="height:435px!important;height:390px;overflow:auto;border:1px solid grey">
                <ul id="treeDemo" class="ztree">
                </ul>
            </div>
            </td>
        </tr>
    </table>
    </form>
</body>
</html>

```

![](https://i.loli.net/2021/01/28/b8RdcgVJP12TnSB.png)
