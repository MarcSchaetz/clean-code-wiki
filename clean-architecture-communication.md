# Communication between objects in a clean architecture

## Step 1
1. User does something which invokes some Controller.
2. The Controller creates a RequestModel data structure that gets passed to the InputBoundary

![Step 1](ca-step-1.svg)

## Step 2
1. The Interactor (UseCase) gets the RequestModel
2. With the data inside the RequestModel the Interactor calls the entities and invokes their application-independent business rules.
(The entities only contain business rules that have nothing to do with automation).
3. The Interactor gathers the information form the entities and invokes its own application specific business rules

![Step 2](ca-step-2.svg)

## Step 3
1. With the data obtained in Step 2 the Interactor creates the ResponseModel data structure.
2. The ResponseModel gets send through the OutputBoundary back to a Presenter or some other object which derives from the OutputBoundary.

![Step 3](ca-step-3.svg)

## Step 4
1. The Presenter uses the data inside the ResponseModel. For example to create strings that can be displayed inside a GUI.

![Step 4](ca-step-4.svg)