# Angular 2/4/5/6 Questions and Answers

I have got these questions from some of my interview experiences and some from internet. Please contribute to make it better by involving [here](https://github.com/gopigoppu/frontend-interview-questions-answers/issues).

I have splited topics based on angular fundamentals.

Also, I have taken questions from this [Yonet REPO](https://github.com/Yonet/Angular-Interview-Questions) to answer it from myside. Credits goes to [contributors](https://github.com/Yonet/Angular-Interview-Questions/graphs/contributors) who spent on this repo to share the questions. Thanks to all. 

## Table of Contents

1. [Architecture Questions](#architecture-questions)
2. [Component Interaction & Templates Questions](#component-interaction--templates-questions)
3. [Directives Questions](#directives-questions)
4. [Api Questions](#api-questions)
5. [Services Questions](#services-questions)
6. [Pipes Questions](#pipes-questions)
7. [Forms Questions](#forms-questions)
8. [Observables & RxJS Questions](#observables--rxjs-questions)
9. [NgModules Questions](#ngmodules-questions)
10. [Routing & Navigation Questions](#routing--navigation-questions)
11. [CSS Questions](#css-questions)
12. [Lifecycle Hooks Questions](#lifecycle-hooks-questions)
13. [Testing Questions](#testing-questions)
14. [Performance Questions](#performance-questions)
1. [Others](#others)



### Architecture Questions

1. How angular app bootstraps?
2. Listout NgModule metadatas? Explain which module or services need to be imported in which metadata?
2. What is a good use case for ngrx/store?
3. Can you talk about a bug related to a race condition, how to solve it and how to test it?
4. What is the difference between a smart/container component and dumb/presentational component? What is a good use case example? What are the advantages?


### Component Interaction & Templates Questions,

1. How to pass data between one component to another? How the changes will trigger while passing data?
2. You have 2 dropdowns. Based on one dropdown selection, you have to render response in another dropdown. How do you achieve?
3. What is Directive in Angular?
4. You have a name in header component and you updating name in profile component. How to automatically trigger changes to headercomponent while updating in profilecomponent?
5. How can you add an active class to a selected element in a list component?
6. What is a template variable. How would you use it?
7. What is the difference of using a property binding verses a function binding on a template?
8. What happens if you subscribe to a data source multiple times with async pipe?
9. What is a component?
10. How do you create two way data binding in Angular?
11. How would you create a component to display error messages throughout your application?
12. What does a lean component mean to you?
13. Which components will be notified when an event is emitted?
14. Tell me about the different ways how you would get data to your components from a service and talk about why would you use one way vs the other?
15. How would you use cached data?

### Directives Questions

1. What is the difference between a component and a directive?
2. What is a structural directive?
3. How do you identify a structural directive in html?
4. When creating your own structural directives, how would you decide on hiding or removing an element? What would be the advantages or disadvantages of choosing one method rather than the other?

### Api Questions

1. What does this code do:
```typescript
@HostBinding('class.valid') isValid;
```
```html
<div *ngIf='someObservableData | async as data; else loading'>{{data}}</div>

<ng-template #loading>
  Loading Data...
</ng-template>
```

2. Why would you use renderer methods instead of using native element methods?
3. How would you control size of an element on resize of the window in a component?
4. What would be a good use for NgZone service?
5. What are the bootstrap options for NgZone? Why would you use them? (Angular 5+)
6. How would you protect a component being activated through the router?
7. How would you insert an embedded view from a prepared TemplateRef?

### Services Questions

1. What is the use case of services?
2. How are the services injected to your application?
3. How do you unit test a service with a dependency?
4. Why is it a bad idea to create a new service in a component like the one below?
```javascript
let service = new DataService();
```

### Pipes Questions

1. What is a pure pipe?
2. What is an async pipe?
3. What kind of data can be used with async pipe?
4. How do you create a custom pipe?
5. How does async pipe prevents memory leeks?

### Forms Questions

1. When do you use template driven vs model driven forms? Why?
2. How do you submit a form?
3. What's the difference between NgForm, FormGroup, and FormControl? How do they work together?
4. What's the advantage of using FormBuilder?
5. How do you add form validation to a form built with FormBuilder?
6. What's the difference between dirty, touched, and pristine on a form element?
7. How can you access validation errors in the template to display error messages?
8. What is async validation and how is it done?

### Observables & RxJS Questions

1. What is Observer?
2. What is Observables? How it differs from Promises?
3. What is mergemap?
4. How to make two api calls parallely?
5. What is the difference between an observable and a subject?
6. What are some of the angular apis that are using observables?
7. How would you cache an observable data?
8. How would you implement a multiple api calls that needs to happen in order using rxjs?
9. What is the difference between switchMap, concatMap and mergeMap?
10. How would you make sure an api call that needs to be called only once but with multiple conditions. Example: if you need to get some data in multiple routes but, once you get it, you can reuse it in the routes that needs it, therefor no need to make another call to your backend apis.
11. How would you implement a brush behavior using rxjs?
12. How would you implement a color picker with rxjs?
13. If you need to respond to two different Observable/Subject with one callback function, how would you do it?(ex: if you need to change the url through route parameters and with prev/next buttons).


### NgModules Questions

1. What is decorator? How this useful in angular?
2. What is the purpose of NgModule?
3. How do you decide to create a new NgModule?
4. What are the attributes that you can define in an NgModule annotation?
5. What is the difference between a module's forRoot() and forChild() methods and why do you need it?
6. What would you have in a shared module?
7. What would you not put shared module?
8. What module would you put a singleton service whose instance will be shared throughout the application (e.g. ExceptionService andLoggerService)?
9. What is the purpose of exports in a NgModule?
10. What is the difference between exports and declerations in NgModule?
11. Why is it bad if SharedModule provides a service to a lazy loaded module?


### Routing & Navigation Questions

1. How do you route in angular?
2. How do you configure params based router and how to get params passed in route?
3. What is `router-outlet`? Why it is needed?
4. What is the difference between RouterModule.forRoot() vs RouterModule.forChild()? Why is it important?
5. How does loadChildren property work?
6. Do you need a Routing Module? Why/not?
7. When does a lazy loaded module is loaded?
8. Below link doesn't work. Why? How do I fix it?
```html
<div routerLink='product.id'></div>
```
9. Can you explain the difference between ActivatedRoute and RouterState?
10. How do you debug router?

### CSS Questions

1. How do you define transition between two states in Angular?
2. How do you define a wildcard state?
3. How would you select a custom component to style it.
4. What pseudo-class selector targets styles in the element that hosts the component?
5. How would you select all the child components' elements?
6. How would you select a css class in any ancestor of the component host element, all the way up to the document root?
7. What selector force a style down through the child component tree into all the child component views?
8. What does :host-context() pseudo-class selector targets?
What does the following css do?
```css
:host-context(.theme-light) h2 {
  background-color: red;
}
```

### Lifecycle Hooks Questions

1. What is the possible order of lifecycle hooks.
When will ngOnInit be called?
2. How would you make use of ngOnInit()?
3. What would you consider a thing you should be careful doing on ngOnInit()?
4. What is the difference between ngOnInit() and constructor() of a component?
5. What is a good use case for ngOnChanges()?

### Testing Questions

1. How do you mock a service to inject in a unit test?
2. How do you mock a module in a unit test?

### Performance Questions

1. What are some of the things that you pay attention to, to make sure your angular application is performant?
2. What tools would you use to find a performance issue in your code?
3. What tools have you used to improve the performance of your application?
4. What are some ways you may improve your website's scrolling performance?
5. Explain the difference between layout, painting and compositing.
6. Have you seen Jeff Cross's NgCruise talk on performance?

### Others

1. What are some of the Angular Style Guide suggestions you follow on your code? Why?
2. Is it important to have a style guide? Why/not?



