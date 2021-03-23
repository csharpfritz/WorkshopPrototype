# Speaker notes

- Introduce @page - explain the difference between routable and non-routable
- Show the Router component in App.razor
- Introduce `@code` - this is like the old `@functions` feature from `.cshtml`. Get users comfortable with the idea of defining properties, fields, methods, even nested classes
- Components are stateful so have a place to keep state in components is useful
- Introduce parameters - parameters should be public
- Introduce using a component from markup in razor - show how to pass parameters
- Introduce @inject and DI - can show how that's a shorthand for a property in @code
- Introduce http + JSON in Blazor (`GetFromJsonAsync`)
- Talk about async and the interaction with rendering 
- Introduce `OnInitializedAsync` and the common pattern of starting async work
- Introduce @layout - mention that `_Imports.razor` is the most common way to hook it up

*demos: All of the above can just be introduced with the template*
