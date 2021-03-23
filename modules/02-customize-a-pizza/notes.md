# Speaker notes

- Introduce event handlers and delegates, different options like method groups, lambdas, event args types, async
- What happens when you update the private state of a component? Walk through and event handler -> update -> re-render
- Defining your own components and accepting parameters
- Mention passing delegates to another component
- Show how re-rendering is different when using delegates, and show `EventCallback` as the fix
- Mention putting common or repeated functionality on model classes
- Introduce input elements and how manual two-way binding can be used (combination of `value` and `@onchange`)
- Show `@bind` as a shorthand for the above
- Show `@bind-value` + `@bind-value:event` as a more speciic version
- Mention that the framework tries to define `@bind` to do the default thing for common input types, but it's possible to specify what you want to bind

*demos: TodoList, with multiple levels of components*
 - Create basic todo list example with TodoItem.cs and TodoList.razor being a self-contained UI
   - See that your "add item" event handler can be an inline lambda, but it's nicer to make a method
   - See how you can make the handler async if you want (e.g., with a Task.Delay) and it re-renders correctly
 - On the textbox where the user enters a new item, also display the current value
   - See it only updates when you tab out
   - Use `@bind-value:event="oninput"`
 - Factor out a `TodoListEditor` component that takes readonly `Text` and `IsDone` parameters
   - Initially, it's a one-way binding. How do we propagate changes back to the parent?
   - Add an `IsDoneChanged` parameter and invoke a callback that manually updates model and calls `StateHasChanged`
   - Replace with `@bind-IsDone` (change param type to `EventCallback<bool>`).
