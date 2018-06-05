var app=angular.module("myApp",[]);
app.controller('appController',[function(){
var self=this;
self.items=[
            {name: 'Computer', price: 500, condition:'New',brand : 'Lenovo', published:'01/11/2015'},
            {name: 'Phone', price: 200, condition:'New',brand : 'Samsung', published:'02/11/2015'},
            {name: 'Printer', price: 300, condition:'New',brand : 'Brother', published:'06/11/2015'},
            {name: 'Dishwasher', price: 250, condition:'Second-Hand',brand : 'WhirlPool', published:'01/12/2015'}
];
self.onItemSelect=function(name){
console.log("congrats You have selected the item",name);
};
}]);
directive('itemWidget',[function(){
  return{
          restrict:'E',
          replace:true,
          transclude:true,
          require:'^shoppingWidget',
          scope:{
                  item='=',
                  promo='@',
                  pickMe:'&onSelect'
                 },
          templateUrl:'shopItem.html',
          link:function(scope,element,attrs,cartCtrl){
                        element.on('click',function(event){
                                                            element.htlm("Thanks for Purchasing this item");
                                                            element.css({color:green;});
                                                            cartCtrl.addItemToCart(scope.item);
                                                            scope.$apply();
                                                           });
                                                     }
       }
 }]);  
 directive('shoppingWidget',[function(){
  return{
          restrict:'E',
          transclude:true,
          templateUrl:'shopDetails.html',
          scope:true,
          controller:['$scope',function($scope){
                                $scope.cart=[];
                                var self=this;
                                self.addItemToCart=function(item){
                                $scope.cart.push(item);};}]
      }
}]);      
