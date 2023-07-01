2.5 Unidirectional Data Flow



Parent to Child Communication (Top-Down)


In React, data flows in a single-direction, from parent to child as props.

App (Parent Component)
	\
	  \   Data (props)
	    \
	 TodoList (Child Component)

function App() { // PARENT COMPONENT 👴🏻
  const [todos, setTodos] = useState([]);
		 
  return (
    <TodoList todos={todos} />
  ); 
}

props ---> { todos }
function TodoList({ todos }) { // CHILD COMPONENT 👶🏻
  return (
    <div>
props.todos
      <ol>{todos.map((todo) =>  <li>{todo}</li>)}
      </ol>
    </div>
  )
}

Child to Parent Communication (Bottom-Up)


If data only goes one way in React, how do we send the data back to the parent?

To flow in reverse, we need to lift state up, by passing a handler function down to the child component.

function App() { // PARENT COMPONENT 👴🏻
  const [todos, setTodos] = useState([]);
		 
  const addTodo = (todo) => setTodos((prevState) => [...prevState, todo])
		 
  return (
    <TodoList todos={todos} onAddTodo={addTodo} />
  ); 
}

function TodoList({ todos, onAddTodo }) { // CHILD COMPONENT 👶🏻
		
  const [newTodo, setNewTodo] = useState('');
			
  return (
    <div>
      <ol>
        {todos.map((todo) => <li>{todo}</li>)}
      </ol>
      <input onChange={(e) => setNewTodo(e.target.value) }>
// On click, onAddToDo is called with the new todo item
// Remember onAddToDo is from the Parent component
// This will update the state in the Parent component
      <button onClick={() => onAddTodo(newTodo) }>
        Add Todo
      </button>
    </div>
  )
}


Presentational and Container Components


The Presentational and Container components is a design pattern that was commonly used in React before Hooks but it is no longer the primary way of structuring a React app, at least not in the old way.

Presentational Component
- primarily for display of data

Container Component
- handles data and provides data to presentational components to display

These concepts were used prior to the introduction of React Hooks but you might still come across them when working on old code like those using class components. In the past we might create a <TodoContainer> and a <Todo>.

For example, you may see this in older code bases:
// TodoList.js (Presentational component)
// This component is used just for rendering UI
// It does not know about or handle state, only gets data from props
function TodoList(props) {
  return (
    <ul>
      {props.todos.map(todo => (
        <li key={todo.id}>
          {todo.text}
          <input type="checkbox" checked={todo.completed}
            onChange={() => props.onTodoToggle(todo.id)} />
        </li>
      ))}
    </ul>
  );
}

// TodoListContainer.js (Container component)
// Responsible for managing data and pass to presentational components
class TodoListContainer extends React.Component {
  state = {
    todos: [
      { id: 1, text: 'Buy groceries', completed: false },
      { id: 2, text: 'Do laundry', completed: true },
    ],
  };

  handleTodoToggle = id => {
    this.setState(state => ({
      todos: state.todos.map(todo =>
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      ),
    }));
  };

  render() {
    return (
      <TodoList todos={this.state.todos} onTodoToggle={this.handleTodoToggle} />
    );
  }
}

<TodoContainer> passes props to <Todo> to render on screen.

But with functional components and React hooks, we do not need to do that anymore i.e. 1 container component for 1 presentational component.  We could just as easily put everything in a <TodoList> component.
function TodoList() {
  const [todos, setTodos] = useState([
    { id: 1, text: 'Buy groceries', completed: false },
    { id: 2, text: 'Do laundry', completed: true },
  ]);

  const handleTodoToggle = id => {
    setTodos(todos =>
      todos.map(todo =>
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      )
    );
  };

  return (
    <ul>
      {todos.map(todo => (
        <li key={todo.id}>
          {todo.text}
          <input
            type="checkbox"
            checked={todo.completed}
            onChange={() => handleTodoToggle(todo.id)}
          />
        </li>
      ))}
    </ul>
  );
}

It is still useful to see some components as UI components though, as you will most likely be using UI libraries or your own custom UI components to render specific parts of your app e.g. <Input>, <Button>, etc.

e.g. using Material UI
return (
    <List>
      {todos.map(todo => (
        <ListItem key={todo.id} disablePadding>
          <Checkbox checked={todo.completed}
            onChange={() => handleTodoToggle(todo.id)} />
          <ListItemText primary={todo.text} />
        </ListItem>
      ))}
    </List>
  );
or our own custom component
function Card({ children }) {
  return <div className="card">{children}</div>;
}
https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0


---




2.6 useContext and useReducer


useState, useEffect and useContext are the basic hooks which you'll use the most often.

There are 7 other hooks that are classified as additional hooks in React's official documentation.
https://reactjs.org/docs/hooks-reference.html

These other hooks you may only use them occasionally or even never have to use them.


useReducer


useState vs useReducer

  const [ state, setState ] = useState(null);
  const [ state, dispatchFn ] = useReducer(reducerFn, initialValue);

The useReducer hook is a more powerful alternative to useState.  

It is used for complex state updates, especially when new state depends on previous state and we have multiple related states.
There is more work to setup as compared to the simpler useState hook.

The useReducer hook takes in:
1. A reducer function
2. An initial state

The reducer function is where we put all our logic to update the state.  This way, the state updating logic is decoupled from the component.

It returns:
1. State snapshot
2. dispatch function - used to dispatch an action

The dispatch function is used in response to events but instead of taking a value like a useState setter, it takes an action object (which has a type and an optional payload).  The action object is tells the reducer how to update the state.

  setScore("123"); // useState setState for comparison

  dispatch({ type: "UPDATE_SCORE", payload: 123 }) // with type and payload
  dispatch({ type: "INCREMENT_SCORE" }) // with type and no payload

A simple useReducer example:

const initialState = { score: 0 };
	
// notice that the state handling logic is outside of the component
const scoreReducer = (state, action) => {
  if(action.type === "INCREMENT") return { score: state.score + 1 };
  if(action.type === "DECREMENT") return { score: state.score - 1 };
  return state;
} 
	
function Game() {
  const [ score, dispatch ] = useReducer(scoreReducer, initialState);
		
  return (
    <div>
      <button onClick={ ()=> dispatch({ type: "INCREMENT" }) }>⬆️ Score</button>
      <button onClick={ ()=> dispatch({ type: "DECREMENT" }) }>⬇️ Score</button>
    </div>
  )
}

But for such a simple state, useState is a better choice:

const [ score, setScore ] = useState(0);
	
return (
  <div>
    <button onClick={ ()=> setScore((prevScore) => prevScore+1 ) }>⬆️ Score</button>
    <button onClick={ ()=> setScore((prevScore) => prevScore-1 ) }>⬇️ Score</button>
  </div>
)

You can see it is a lot more work to setup useReducer which is not worth the effort just for a single state.

For more complicated logic e.g. shopping cart with discount percentages which varies according to the quantity purchase, this could be a good use case for useReducer.  Because we can write all that logic in the reducer and use the related states in the same state object.

There is also always the option of using useState with a state object instead of multiple states e.g.

const [ form, setForm ] = useState({ firstName: "", lastName: "" })
	
const handleFormUpdate = (e) => {
  setForm((prevForm)=> {
    return {
      ...prevForm,
      [e.target.name]: e.target.value
    }
  })	
}

useState is actually just "sugar" for useReducer i.e. useState is built on useReducer.

Another benefit to using useReducer is that setting of the state is only done in the reducer, so if you work on the code with other developers, the logic for handling that state update would not be accidentally changed.  You or other developers will also not be able to set the state directly by accident.

e.g.
// Using useState - any developer can set any value by calling the setter function directly!
setDiscount(20);
	
// Using useReducer
dispatch( { type: 'UPDATE_DISCOUNT', value: 20 });
	
// In the reducer, we can validate before setting the value
if (action.type === 'UPDATE_DISCOUNT') 
  // Prevent discount from being set since the qty condition is not met
  if (prevState.qty < 5) return state; 

  // Only proceed with state update if the condition is met
  else return {
    ...state,
    discount: 20,
  }

Generally, for simple apps and logic, use useState.  Once there are a few related states and a bit more logic, you can use useState with objects.  Beyond this, you can start looking into useReducer.



Context


In React, we usually have to manage different type of states:
- local states (within a component)
- cross-component states (shared between related components)
- app-wide or global state (shared throughout entire app)

For local state, we use useState.  But with some components, we might have to do a few levels of props forwarding and then lifting the state back up.  Some components in between have no use for the props but are just responsible for forwarding them.


How Do We Use Context?


1. Create a context store (usually in store or context folder)

store/auth-context.js  

2. Set up our context file

import { createContext, useState } from "react";

// Create our context
export const AuthContext = createContext();

// Create the context provider component to manage states	
export function AuthContextProvider({children}) {

  // Define states to manage in our context
  const [ isLoggedIn, setIsLoggedIn ] = useState(false);

  // Define handler methods if needed	
  const loginHandler = () => setIsLoggedIn(true);
  const logoutHandler = () => setIsLoggedIn(false);
		
  // Context object to be passed to the provider
  const context = { 
    isLoggedIn: isLoggedIn,
    loginHandler: loginHandler,
    logoutHandler: logoutHandler
  }
	
  return <AuthContext.Provider value={context}>{children}</AuthContext.Provider>
}
	



3. Wrap the app or components that needs the context

<AuthContextProvider>
  <App />
</AuthContextProvider>


4. Use the useContext hook to access the context value


import { useContext } from "react";
	
import { AuthContext } from "./store/auth-context";
	
function App() {
		
  const authCtx = useContext(AuthContext);

  return {
    {authCtx.isLoggedIn && <h1>You are logged in ✅</h1>}
    {!authCtx.isLoggedIn && <h1>You are logged out ⛔️</h1>}	
  }
	
}





More Info on Context


Caveat about over-using useContext - it is not designed for high frequency updates.  

Because every time the context state changes, all the components wrapped by the context provider which also consumes the context also re-renders.

It is more suited for state changes that don't happen with high frequency e.g. changing dark/light mode, storing authentication state (isLoggedIn = true, role = admin).

For this reason, it is more useful for states that are read more often than written.  

When you use it, only wrap those related components as far as possible.

E.g. if you have a shopping filter that "remembers" a user's filter such as "price <= 500", try not to store all that context state with other context states.  
Do not wrap at the root like this.

<OverallAppProvider>
<UiProvider>
<AuthProvider>
  <App /> 
</OverallAppProvider>

	
instead create a context for only those components that need it and wrap it only lowest level possible.
	

<ShoppingFilterProvider> // has ctx.Budget = 500
  <ShoppingMenu /> // sets and displays items <= 500
  <RecommendedItems /> // lists under items <= 500
</ShoppingFilterProvider>

	


---



Practice Exercise


You can use the last game app we did to work on this.


Part 1 - useReducer

1. Refactor number guessing game using useReducer
2. Add scoring - Game starts with 20 points, each wrong guess subtracts the score by 1


Part 2 - useContext

1. Create a component ScoreHistory to record the score with React Context
- when the user clicks on New Game, save the score
- note that the score is only saved when the user has completed the game



