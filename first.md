[TOC]

# 登录界面  

1. 页面设置

* 标题  

  ```  
  <h1>登录</h1>
  ```

  

* 账号、密码  

  ```  
  <p>账号:<input type="text" id="account" name="账号" placeholder="请输入账号"/></p>
  <p>密码:<input type="password" id="password" name="密码" placeholder="请输入密码"/></p>
  ```

  

* 按钮  

  ```  
  <p><input type="button" id="sign in" value="登录"/>  <input type="reset" value="重置"/></p>
  ```

    

2. 页面跳转  

   ```  
   document.getElementById("sign in").onclick=function(){
   	var a = document.getElementById("account").value;
   	var b = document.getElementById("password").value;
   	if (a=="123456" && b=="123456"){
   	window.location.href="bill.html";
   	}else{
       window.location.href="false.html"
   	}
   ```

  

***



# 登录失败界面  

1. 内含信息(正确账号、密码)  

   ```  
   <p style="text-align:center">账号:123456</p>
   <p style="text-align:center">密码:123456</p>
   ```



2. 返回按钮  

   ```  
   <p><input type="button" value="返回" style="text-align:center" onclick="location.href='denglu.html'"></p>
   ```

   

***



# 账单界面  

1. 表头  

   > 设置日期、收入、饭钱、水电费、交通费、生活用品、学习、爱好、其他、备注、总计  

2. 通过首行添加数据  

   ``` 
    <tr>
     <td><input type="date" id="myDate" style="width: 180px;"/></th>
     <td><input type="text" id="myMoney1"/></th>
     <td><input type="text" id="myMoney2"/></th>
     <td><input type="text" id="myMoney3"/></th>
     <td><input type="text" id="myMoney4"/></th>
     <td><input type="text" id="myMoney5"/></th>
     <td><input type="text" id="myMoney6"/></th>
     <td><input type="text" id="myMoney7"/></th>
     <td><input type="text" id="myMoney8"/></th>
     <td style="width: 180px;"><input type="text" id="beizhu" style="width: 180px;"/></th>
     <td></td>
    </tr>
   ```

  

3. 通过获取首行数据添加记录，并计算总计一栏  

   ``` 
   function addtr(){
      var newTr = document.getElementById("testTbl").insertRow();
      var newTd0 = newTr.insertCell();
      var newTd1 = newTr.insertCell();
      var newTd2 = newTr.insertCell();
      var newTd3 = newTr.insertCell();
      var newTd4 = newTr.insertCell();
      var newTd5 = newTr.insertCell();
      var newTd6 = newTr.insertCell();
      var newTd7 = newTr.insertCell();
      var newTd8 = newTr.insertCell();
      var newTd9 = newTr.insertCell();
      var newTd10 = newTr.insertCell();
      newTd0.innerHTML= document.getElementById("myDate").value;
      newTd1.innerHTML= document.getElementById("myMoney1").value;
      newTd2.innerHTML= document.getElementById("myMoney2").value;
      newTd3.innerHTML= document.getElementById("myMoney3").value;
      newTd4.innerHTML= document.getElementById("myMoney4").value;
      newTd5.innerHTML= document.getElementById("myMoney5").value;
      newTd6.innerHTML= document.getElementById("myMoney6").value;
      newTd7.innerHTML= document.getElementById("myMoney7").value;
      newTd8.innerHTML= document.getElementById("myMoney8").value;
      newTd9.innerHTML= document.getElementById("beizhu").value;
      var myMoney1 = document.getElementById("myMoney1");
      var myMoney2 = document.getElementById("myMoney2");
      var myMoney3 = document.getElementById("myMoney3");
      var myMoney4 = document.getElementById("myMoney4");
      var myMoney5 = document.getElementById("myMoney5");
      var myMoney6 = document.getElementById("myMoney6");
      var myMoney7 = document.getElementById("myMoney7");
      var myMoney8 = document.getElementById("myMoney8");
      var money1 = document.getElementById("myMoney1").value;
      var money2 = document.getElementById("myMoney2").value;
      var money3 = document.getElementById("myMoney3").value;
      var money4 = document.getElementById("myMoney4").value;
      var money5 = document.getElementById("myMoney5").value;
      var money6 = document.getElementById("myMoney6").value;
      var money7 = document.getElementById("myMoney7").value;
      var money8 = document.getElementById("myMoney8").value;
      var k = parseInt ( money1 );
      var l = parseInt ( money2 );
      var m = parseInt ( money3 );
      var n = parseInt ( money4 );
      var o = parseInt ( money5 );
      var p = parseInt ( money6 );
      var q = parseInt ( money7 );
      var r = parseInt ( money8 );
      newTd10.innerHTML= k - l - m - n - o - p - q -r ;
   }
   ```

   

4. 删除记录  

   > 通过输入行数删除指定行数据

   ```  
   <input type="text" id="delTextId" style="width: 80px;" />
   <input type="button" value="删除记录" style="width: 80px;" onclick="delRow()" />
   ```

   ```  
   function delRow() {
               var rowIndex = document.getElementById("delTextId").value;
               var tb = document.getElementById("testTbl");
               tb.deleteRow(rowIndex);
   ```

   

***



# 不足  

1. 通过获取第一行输入数据的方法添加数据后每一行添加的记录都可计算，但是这样做没法指定位置修改数据（无法获得id）。  
2. localStorage还是不会用，感觉还是不知道怎么与我前面的部分结合起来。