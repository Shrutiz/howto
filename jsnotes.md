##Variable declaration
* var- declares a variable with function scope
* let- declares a variable with block scope
* const- declares a read only constant
Example:

	var x= 7;
	let y= "hey";
	const s= 2;

####Hoisting
We can refer to a variable declared later, without getting an exception

#### Dynamic type conversion
	var a= "42";
	a="hello";

## Conditional Statements
###If statement
	if(x>y){
	// statements

	}
	else{
	// statements
	}

###Switch statement
	switch (fruittype) {
			case "Oranges":
				console.log("Oranges are $0.59 a pound.");
			break;
			case "Apples":
				console.log("Apples are $0.32 a pound.");
			break;
		}
## Creating objects
	var car= new Object();
	car.make= 'Honda';
	car.model= 'City';
####OR
	var car={make:'Honda',model='City'};

## If we would like to define a type, i.e., like a class we use functions
	function Car(make,model)
	{
		this.make= make;
		this.model= model;
		}

#### Then we can create objects of type Car
	var mycar= new Car('Honda','City');

##We can add more attributes & methods to the object by keyword **prototype**
	Car.prototype.color= null;
	mycar.color= 'Black';

	Car.prototype.show= function(){
		console.log("This is a " + this.color +" " + this.make+" "+ this.model);
		}
