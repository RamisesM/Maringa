### Software architecture key principles

#### Key design principles

- Separation of concerns.
- Single Responsibility principle.
- Principle of Least Knowledge (also known as the Law of Demeter or LoD).
- Don’t repeat yourself (DRY). Don't repeat functionalities.
- Minimize upfront design. YAGNI ("You ain’t gonna need it").

#### Design practices

- Keep design patterns consistent within each layer.
- Do not duplicate functionality within an application.
- Prefer composition to inheritance.
- Establish a coding style and naming convention for development.
- Maintain system quality using automated QA(quality analysis) techniques during
development.
- Consider the operation of your application.

#### Application Layers

- Separate the areas of concern.
- Be explicit about how layers communicate with each other.
- Use abstraction to implement loose coupling between layers.
- Do not mix different types of components in the same logical layer.
- Keep the data format consistent within a layer or component.

#### Components, Modules and Functions

- A component or an object should not rely on internal details of other
components or objects.
- Do not overload the functionality of a component.
- Understand how components will communicate with each other.
- Keep crosscutting code abstracted from the application business logic as far
as possible.
- Define a clear contract for components.

#### Key Design considerations

- Determine the Application Type
- Determine the Deployment Strategy
- Determine the Appropriate Technologies
- Determine the Quality Attributes
- Determine the Crosscutting Concerns (shit like log, exceptions, etc.. -> It is
good to be centralized)


continue: https://msdn.microsoft.com/en-us/library/ee658117.aspx
