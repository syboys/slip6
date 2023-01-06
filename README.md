# slip6



q.1. Write a Java Program to implement command pattern to test Remote Control

q.2. Write a python program to implement Polynomial Linear Regression for given dataset

Q.3. Create a Node.js file that opens the requested file and returns the content to the client.
If anything goes wrong, throw a 404 error. 







q1) Write a Java Program to implement command pattern to test Remote Control

:

interface Command {
 public void execute();
}
class Light {
 public void on(){
 System.out.println("Light is on");
 }
 public void off()
 {
 System.out.println("Light is off");
 }
}
 class LightOnCommand implements Command {
 Light l1;

 public LightOnCommand(Light a) {
 this.l1 = a;
 }

 public void execute() {
 l1.on();
 }

}
 class LightOffCommand implements Command {
Light l1;
public LightOffCommand(Light a) {
this.l1 = a;
}
public void execute() {
l1.off();
}
}
 class SimpleRemoteControl {
 Command slot;
public SimpleRemoteControl() {}

 public void setCommand(Command command) {
 slot = command;
 }

 public void buttonWasPressed() {
 slot.execute();
 }

}
public class Main {
 public static void main(String[] args) {
 SimpleRemoteControl r1 = new SimpleRemoteControl();
 Light l1 = new Light();

LightOnCommand lo = new LightOnCommand(l1);
 r1.setCommand(lo);
 r1.buttonWasPressed();
LightOffCommand lO = new LightOffCommand(l1);
r1.setCommand(lO);
r1.buttonWasPressed();

 }
} 


q2)Write a python program to implement Polynomial Linear Regression for given dataset
:

import numpy as np
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

# Load the dataset
X = np.array([1, 2, 3, 4, 5]).reshape(-1, 1)
y = np.array([2, 3, 4, 5, 6])

# Transform the dataset to include polynomial features
poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)

# Fit a linear regression model to the transformed dataset
model = LinearRegression()
model.fit(X_poly, y)

# Predict on a new input
x_new = np.array([6]).reshape(-1, 1)
x_new_poly = poly.transform(x_new)
y_pred = model.predict(x_new_poly)

print(f'Prediction: {y_pred[0]:.2f}')


Q.3. Create a Node.js file that opens the requested file and returns the content to the client.
If anything goes wrong, throw a 404 error

:
var http=require('http');
var fs=require('fs');
var url=require('url');
http.createServer(function (request,response)
{
 var q=url.parse(request.url,true);
 var filename="."+q.pathname;
 fs.readFile(filename,function(error,data)
 {
 if(error)
 {
 response.writeHead(404,{'content-type':'text/html'});
 return response.end("404 not found");
 }
 response.writeHead(200,{'content-type':'text/html'});
 response.write(data);
 response.end();
});
}).listen(8000);

SAMPLE 1
WHAT IS GOOGLE?
Google is a popular internet search engine. It scans the Web to
find Web pages that are relevant to the words you have typed in
the search box.






