# advance_fultter_ch_1
# Switch Dark Theme to Light Theme

<img src="https://github.com/Eku0425/advance_fultter_ch_1/assets/149374328/3d3050c0-cd7b-4458-a56c-d48c1733b7aa" height=25% width=25%>
<img src="https://github.com/Eku0425/advance_fultter_ch_1/assets/149374328/f2f2c68f-bf63-43bd-87e5-55859ab89628" height=25% width=25%>

# Exampal
theme: ThemeData.light(),
darkTheme: ThemeData.dark(),
themeMode: isDark ? ThemeMode.dark : ThemeMode.light,

 If you want to use dark mode, just add darkTheme: ThemeData. dark()










 State management:-
The state management is one of the most popular and necessary processes in the lifecycle of an application.
According to official documentation, Flutter is declarative.
It means Flutter builds its UI by reflecting the current state of your app.
The following figure explains it more clearly where you can build a UI from the application state.
The setState() function allows us to set the properties of the state object that triggers a redraw of the UI.
There are Two way to represent a State management :-
Treditional :-

State management involves handling and updating this data to reflect changes in the application's UI.

setState();
Provider StateManagement :-

Provider is a Flutter package that simplifies state management by offering a straightforward approach based on the InheritedWidget mechanism.

ChangeNotifier
ChangeNotifierProvider
Consumer
ChangeNotifier :-
ChangeNotifier is a simple class, which provides change notification to its listeners.
It is easy to understand, implement, and optimized for a small number of listeners.
It is used for the listener to observe a model for changes.
In this, we only use the notifyListener() method to inform the listeners.
class Counter with ChangeNotifier {  
  int _counter;  
  
  Counter(this._counter);  
  
  getCounter() => _counter;  
  setCounter(int counter) => _counter = counter;  
  
  void increment() {  
    _counter++;  
    notifyListeners();  
  }  
  
  void decrement() {  
    _counter--;  
    notifyListeners();  
  }  
}  


ChangeNotifierProvider :-
ChangeNotifierProvider is the widget that provides an instance of a ChangeNotifier to its descendants.
It comes from the provider package.
The following code snippets help to understand the concept of ChangeNotifierProvider.
void main() {  
  runApp(  
    MultiProvider(  
      providers: [  
        ChangeNotifierProvider(builder: (context) => Counter()),  
        Provider(builder: (context) => SomeOtherClass()),  
      ],  
      child: MyApp(),  
    ),  
  );  
}  
Consumer
It is a type of provider that does not do any fancy work.
It just calls the provider in a new widget and delegates its build implementation to the builder.
The following code explains it more clearly.
return Consumer<Counter>(  
  builder: (context, count, child) {  
    return Text("Total price: ${count.total}");  
  },  
);  
Provider Tree :-




