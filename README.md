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
