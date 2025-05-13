# Lifting state up

Sometimes, two sibling components need to share state.

Sibling components are components that share the same immediate parent in the component hierarchy.

In these situations where sibling components need to share state, we fix this by lifting state to their parent component.

The state is the passe to the sibling components that need it via props.