# AJS-p1-p6
////////////////////Program1
<!DOCTYPE html>
<html>
    <head>
        <title>LAB1 PROGRAM</title>
<script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        	</script>
        	<script>
            	var app=angular.module("myApp",[]);
            	app.controller("myCntrl",function($scope){
                		$scope.firstname="Thanuja"
                		$scope.lastname="N"
           	 });
        	</script>
    </head>
    <body ng-app="myApp">
        <h2>Angular JS Application to display Full Name</h2>
        <div ng-controller="myCntrl">
            Enter First Name: <input type="text" ng-model="firstname" /><br />
            Enter Last Name: <input type="text" ng-model="lastname" /><br />
            Your Full Name: {{firstname +" "+ lastname}}
        </div>
    </body>
    </html>



//////////////////Program2

<!DOCTYPE html>
<html>
    <head>
        <title>LAB2 PROGRAM </title>
<script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script>
            var app=angular.module("myApp",[]); 
            app.controller("myCntrl",function($scope){
                $scope.shoppingitems=['Eggs','Bread','Milk','Curd']

            $scope.additem=function(){
                if($scope.newitem && $scope.shoppingitems.indexOf($scope.newitem)==-1)
                {
                    $scope.shoppingitems.push($scope.newitem)
                    $scope.newitem=""
                }
                else
                {
                    if($scope.newitem)
                        alert("This item is already their in the Shopping List")
                    else
                        alert("Please enter an item to add")
                }
            }

            $scope.removeitem=function(){
                if($scope.shoppingitems.indexOf($scope.selectitem)==-1)
                    alert("Please select an item to remove")
                else
                {
                    var index=$scope.shoppingitems.indexOf($scope.selectitem)
                    $scope.shoppingitems.splice(index,1)
                    $scope.selectitem=""
                }
            }
            });
        </script>
    </head>
    <body ng-app="myApp"> 
        <h2>Shopping Application</h2>
        <h4>List of Shopping Items</h4>
        <div ng-controller="myCntrl">
            <ul>
                <li ng-repeat="item in shoppingitems">{{item}}</li>
            </ul>
            Enter a Item to Add:<input type="text" ng-model="newitem">
            <button ng-click="additem()">Add Item</button> <br/><br />

Select an Item to remove:<select ng-model="selectitem" ng-options="item for item in shoppingitems" ></select>
            <button ng-click="removeitem()">Remove Item</button>
        </div>
    </body>
    </html>







///////////////////program3

<!DOCTYPE html>
<html>
      <head>
        <title>LAB3 PROGRAM </title>
        <script type="text/javascript" 	src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script>
            var app=angular.module("myApp",[]); 
            app.controller("myCntrl",function($scope){
                $scope.num1=0
                $scope.num2=0
                $scope.result=0
                $scope.operator="add"

                $scope.compute=function()
   {
                    switch($scope.operator)
{
                        case 'add': $scope.result=$scope.num1+$scope.num2
                                    break
                        case 'sub': $scope.result=$scope.num1-$scope.num2
                                    break
                        case 'mul': $scope.result=$scope.num1*$scope.num2
                                    break
                        case 'div': if($scope.num2==0)
                                    alert("Divide by zero error")
                                    else
                                        $scope.result=$scope.num1/$scope.num2
                                    break
                        }
                }
            });
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>SIMPLE CALCULATOR</h1>
        <div ng-controller="myCntrl">
            Enter First Number: <input type="number" ng-model="num1">
            Select Operator:<select ng-model="operator">
                <option value="add">+</option>
                <option value="sub">-</option>
                <option value="mul">*</option>
                <option value="div">/</option>
            </select>
            Enter Second Number: <input type="number" ng-model="num2"><br/><br />
            <button ng-click="compute()">COMPUTE</button> <br />
            {{num1 +" "+operator+" "+num2 +" = "+result}}
        </div>
    </body>
    </html>





////////Program4

<!DOCTYPE html>
<html>
    <head>
        <title> LAB4 PROGRAM </title>
   <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script>
            var app=angular.module("myApp",[]); 
            app.controller("myCntrl",function($scope){
                $scope.num=0
                $scope.result=0
                
                $scope.factorial=function(){
                    if($scope.num==0)
                        $scope.result=1
                    else
                    {
                        $scope.fact=1
                        for(var i=$scope.num; i>=1;i--)
                            $scope.fact=$scope.fact*i
                        $scope.result=$scope.fact
                    }
                }

                $scope.square=function(){
                    $scope.result=$scope.num*$scope.num
                }
            });
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>FACTORIAL AND SQUARE APPLICATION</h1>
        <div ng-controller="myCntrl">
            Enter the Number: <input type="number" ng-model="num">
            <button ng-click="factorial()">COMPUTE FACTORIAL</button> 
            <button ng-click="square()">COMPUTE SQUARE</button> <br />
            {{result}}
        </div>
    </body>
    </html>




/////////////////proram5

<!DOCTYPE html>
<html>
    <head>
        <title>LAB5 PROGRAM</title>
        <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]); 
        app.controller("myCntrl",function($scope){
               $scope.stdata=[] 
               $scope.generatedata=function(){
                $scope.stdata=[]    
                for(var i=1;i<=$scope.num;i++)
                {        var stud={"SLNO":i,"NAME":'Student-'+i,"CGPA":(Math.random()*10).toFixed(2)}
                         $scope.stdata.push(stud)
                } 
               }   
            });        
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>STUDENT DETAILS APPLICATION</h1>
        <div ng-controller="myCntrl">
            Enter the Number of Students to Generate the data:<input type="number" ng-model="num">
            <button ng-click="generatedata()">GENERATE DATA</button><br/>
            <table border="1" ng-show="stdata.length>0">
                <tr>
                    <th>SL.NO.</th>
                    <th>NAME</th>
                    <th>CGPA</th>
                </tr>
                <tr ng-repeat="std in stdata">
                    <td>{{std.SLNO}}</td>
                    <td>{{std.NAME}}</td>
                    <td>{{std.CGPA}}</td>
                </tr>
            </table><br/>
            Number of Students={{stdata.length}}
        </div>
    </body>
    </html>







////////////program6



<!DOCTYPE html>
<html>
    <head>         <title>LAB6 PROGRAM</title>
        <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]); 
            app.controller("myCntrl",function($scope){
               $scope.tasks=[{"TITLE":"Task-1","COMPLETED":true,"EDITING":false},
                             {"TITLE":"Task-2","COMPLETED":false,"EDITING":false},
                             {"TITLE":"Task-3","COMPLETED":true,"EDITING":false}
                            ]

                $scope.addtask=function(){
                    if($scope.newtask){
                    var t={
                        'TITLE':$scope.newtask,
                        'COMPLETED':false,
                        'EDITING':false
                    }
                    $scope.tasks.push(t)
                }
                else
                    alert("Please enter the task to add")
                }

                $scope.edittask=function(task)
                {
                    task.EDITING=true
                }

                $scope.turnOffEditing=function(task)
                {
                    task.EDITING=false
                }

                $scope.deletetask=function(task)
                {
                    var index=$scope.tasks.indexOf(task)
                    $scope.tasks.splice(index,1)
                }
            });        
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>TO DO APPLICATION</h1>
        <div ng-controller="myCntrl">
            Enter the Name of the Task:<input type="text" ng-model="newtask">
            <button ng-click="addtask()">ADD TASK</button><br/>
            <ul>
                <li ng-repeat="task in tasks">
                    <input type="checkbox" ng-model="task.COMPLETED">
                    <span ng-show="!task.EDITING">{{task.TITLE}}</span>
                    <input type="text" ng-show="task.EDITING" ng-model="task.TITLE" ng-blur="turnOffEditing(task)">
                    <button ng-click="edittask(task)">EDIT</button>
                    <button ng-click="deletetask(task)">DELETE</button>
                </li>
            </ul>
        </div>
    </body>
    </html>





    /////////////////////////program7

    <!DOCTYPE html>
<html>
    <head>
        <title>LAB7 PROGRAM</title>
  <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]);             
        app.controller("myCntrl",function($scope)
        {
               $scope.users=[
{"name":"Prof. N. Thanuja","email":"thanu.anu21@gmail.com","editing":false},
                        {"name":"Prof. Anu","email":"anu22@gmail.com","editing":false},
                        {"name":"Prof. Janutha","email":"janutha@gmail.com","editing":false}]
                            
                $scope.createuser=function()
                {
                    if($scope.newusername && $scope.newuseremail)
                    {
                        var u={
                            'name':$scope.newusername,
                            'email':$scope.newuseremail,
                            'editing':false
                            }
                        $scope.users.push(u)
                        $scope.newusername=' '
                        $scope.newuseremail=' '
                    }
                    else
                        alert("Please provide the User Name and Email id")
                }

                $scope.readuser=function(user)
                {
                    user.editing=true
                }

                $scope.updateuser=function(user)
                {
                    user.editing=false 
                }

                $scope.deleteuser=function(user)
                {
                    var confirm=prompt("Are you sure you want to delete")
                    if(confirm=="Yes")
                    {
                        var index=$scope.users.indexOf(user)
                        $scope.users.splice(index,1)
                    }
                }
            });        
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>USER MANAGEMENT APPLICATION</h1>
        <div ng-controller="myCntrl">
           Enter the User Name:<input type="text" ng-model="newusername" />
           Enter the User Email:<input type="email" ng-model="newuseremail" />
           <button ng-click="createuser()">CREATE</button><br />
            <ul>
                <li ng-repeat="user in users">
<span ng-show="!user.editing">{{user.name}}</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                    <input type="text" ng-show="user.editing" ng-model="user.name" />
<span ng-show="!user.editing">{{user.email}}</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                    <input type="text" ng-show="user.editing" ng-model="user.email" />
                    <button ng-click="readuser(user)">READ</button>
                    <button ng-click="updateuser(user)">UPDATE</button>
                    <button ng-click="deleteuser(user)">DELETE</button>
                    <br />
                </li>
            </ul>
        </div>
    </body>
    </html>

    
    
    /////////////////////////program8

    <!DOCTYPE html>
<html>
    <head>
        <title>LAB8 PROGRAM</title>
        <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]);             
        app.controller("myCntrl",function($scope)
        {
               $scope.username=''
               $scope.password=''  
               $scope.noattempts=0
               $scope.login=function()
               {
                //console.log("Inside login function")
                if($scope.username=="thanuja" && $scope.password=="12345678")
                {
                    alert("Login Successful")
                }
                else{
                    $scope.noattempts++
                    if($scope.noattempts<=3)
                    {
                        alert("Incorrect username/password! Attempt No. "+$scope.noattempts)
                    }
                    else
                    {
                        document.getElementById("loginbutton").disabled=true
                    }
                }
                }
            });        
        </script>
        <style>
            .error-message{color:red; font-size:20px}
        </style>
    </head>
    <body ng-app="myApp"> 
        <h1>ANGULARJS LOGIN FORM</h1>
        <form name="loginform" ng-submit="submitform()">
            <div ng-controller="myCntrl">
                Enter User Name:<input type="text" name="username" ng-model="username" ng-minlength="5" ng-maxlength="8" required>
                <span class="error-message" ng-show="loginform.username.$error.required && loginform.username.$dirty">User Name is Required</span>
                <span class="error-message" ng-show="loginform.username.$error.minlength">Minimum Length Must be 5</span>
                <span class="error-message" ng-show="loginform.username.$error.maxlength">Maximum Username Length is Limited to 8</span><br/><br/>
                Enter Password:<input type="password" name="password" ng-model="password" ng-minlength="5" ng-maxlength="8" required>
                <span class="error-message" ng-show="loginform.password.$error.required && loginform.password.$dirty">Password is Required</span>
                <span class="error-message" ng-show="loginform.password.$error.minlength"> Minimum Password Length Must be 5</span>
                <span class="error-message" ng-show="loginform.password.$error.maxlength"> Maximum Password Length is Limited to 8</span><br/><br/>
                <button type="submit" ng-disabled="loginform.$invalid" ng-click="login()" id="loginbutton">Login</button> 
            </div>
        </form>
    </body>
</html>


    
    /////////////////////////program9

    <!DOCTYPE html>
<html>
    <head>
        <title>LAB9 PROGRAM</title>
  <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]);
        app.controller("myCntrl",function($scope)
        {
            $scope.emplist=[{'name':'Thanu','salary':50000},
                            {'name':'Arya','salary':40000},
                            {'name':'Sri','salary':80000},
                            {'name':'Chandu','salary':80000},
                            {'name':'Kumar','salary':70000},
                            {'name':'Anu','salary':60000},
                            {'name':'Pramod','salary':30000},
                            {'name':'Madhu','salary':90000},
                            {'name':'Mohan','salary':20000},
                            {'name':'Shiva','salary':100000}]

            $scope.clearfilters=function()
            {
                $scope.searchname=""
                $scope.searchsalary=""
            }
            });      
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>EMPLOYEE SEARCH APPLICATION</h1>
        <div ng-controller="myCntrl">
            Search Employee by Name:<input type="text" ng-model="searchname">
            Search Employee by Salary:<input type="number" ng-model="searchsalary">
            <button ng-click="clearfilters()">CLEAR FILTERS</button>
            <h3>List of Employees</h3>
            <table border="1">
                <tr>
                    <th>SL.NO.</th>
                    <th>EMPLOYEE NAME</th>
                    <th>SALARY</th>
                </tr>
                <tr ng-repeat="emp in emplist | filter:{name:searchname,salary:searchsalary}" >
                    <td>{{$index+1}}</td>
                    <td>{{emp.name}}</td>
                    <td>{{emp.salary}}</td>
                </tr>
            </table>
        </div>        
    </body>
</html>


    
    /////////////////////////program10

    <!DOCTYPE html>
<html>
    <head>
        <title>LAB10 PROGRAM</title>
        <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]); 
        app.controller("myCntrl",function($scope)
        {
            $scope.itemlist=['Pen','Pencil','Book','Eraser']
            $scope.add=function()
            {
                if($scope.additem)
                {
                    if($scope.itemlist.indexOf($scope.additem)==-1)
                    {
                        $scope.itemlist.push($scope.additem)
                    }
                    else
                        alert("This item is already exists in the collection")
                }
                else
                    alert("Please enter an item to add")
            }

            $scope.remove=function(item)
            {
                confirm=prompt("Are you sure you want to delete "+item)
                if(confirm=='Yes')
                {
                    var index=$scope.itemlist.indexOf(item)
                    $scope.itemlist.splice(index,1)
                }
            }
            });      
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>ITEM MANAGEMENT APPLICATION</h1>
        <div ng-controller="myCntrl">
            Enter an Item to add:<input type="text" ng-model="additem" />
            <button ng-click="add()">ADD</button>
            <h3>List of Items</h3>
            <table border="1">
                <tr>
                    <th>SL.NO.</th>
                    <th>ITEM</th>
                    <th>Remove</th>
                </tr>
                <tr ng-repeat="item in itemlist">
                    <td>{{$index+1}}</td>
                    <td>{{item}}</td>
                    <td><button ng-click="remove(item)">REMOVE</button></td>
                </tr>
            </table>
               <br/><br/>         
            Total Number of Items=<b>{{itemlist.length}}</b>
        </div>        
    </body>
</html>


    
    /////////////////////////program11

    <!DOCTYPE html>
<html>
    <head>
        <title>LAB11 PROGRAM</title>
        <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]); 
        app.controller("myCntrl",function($scope)
        {
            $scope.stud=['thanuja','chandu','mohana','arun','shiva']
        });      
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>STUDENT DEATILS IN UPPERCASE</h1>
        <div ng-controller="myCntrl">
            <table border="5">
                <tr>
                    <th>SL.NO.</th>
                    <th>NAME</th>
                </tr>
                <tr ng-repeat="std in stud">
                    <td>{{$index+1}}</td>
                    <td>{{std | uppercase}}</td>
                </tr>
            </table>
        </div>        
    </body>
</html>


    
    /////////////////////////program12

    <!DOCTYPE html>
<html>
    <head>
        <title>LAB12 PROGRAM</title>
        <script type="text/javascript" src="https:\\ajax.googleapis.com\ajax\libs\angularjs\1.8.2\angular.min.js">
        </script>
        <script> 
        var app=angular.module("myApp",[]); 
        app.controller("myCntrl",function($scope)
        {
            $scope.curdate=new Date();
        });
        </script>
    </head>
    <body ng-app="myApp"> 
        <h1>DATE IN DIFFERENT FORMATS</h1>
        <div ng-controller="myCntrl">
            Current Date and Time: {{curdate}}<br /><br />
            
            Short Date:{{curdate|date:'short'}}<br /><br />
            Medium Date:{{curdate|date:'medium'}}<br /><br />
            Long Date:{{curdate|date:'longDate'}}<br /><br />
            
            Short:{{curdate | date:'short'}}<br /><br />
            Medium:{{curdate | date:'medium'}}<br /><br />
            Full Date:{{curdate | date:'fullDate'}}<br /><br />

            Short Time:{{curdate | date:'shortTime'}}<br /><br />
            Medium Time:{{curdate | date:'mediumTime'}}<br /><br />
            
            Today: {{curdate|date:'dd.MMMM.yyyy'}}<br /><br />
            Today-1: {{curdate|date:'dd.MMM.yy'}}<br /><br />
            Today-2: {{curdate|date:'dd.MM.y'}}<br /><br />
            Today-3: {{curdate|date:'d.M.y'}}<br /><br />
            Today-4: {{curdate|date:'d.MM.y-hh.mm.ss'}}<br /><br />
            Today-5: {{curdate|date:'dd.MM.y-h.m.s'}}
        </div>        
    </body>
</html>


    
