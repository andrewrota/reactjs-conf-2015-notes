**Data comparability** from a single source of truth

What we want is referential equality for deep objects.

Immutable model: you have this really powerful guarentee as a developer to know if something needs to change.

Referential equality is like checking the receipt of a return at a store.

**Controlled scrolling**

Wanted to simulate overflow auto.  Only need one parameter: scrollTop that's going to be changing all the time.

Separate table code from scrolling code.

Not quite as intuitive is that be separating code you also get perf.  Since scrollTop is updating frequently you don't want to render your table if you don't need.  Use PureRenderMixin for the inner table.  Get performance and separation of concerns.

fb experienced this when they had really bad framerate.  They realized they were rendering every row and cell each time with each scroll.

**Children create deep update trees**

When you make a change to a react component you compare two trees and produce an update tree.  The more nodes in the update tree the slower the update pass will be.

It's really easy to get to the point where it gets hard to maintain.  It's easy to snowball and get to the point where you're threading things down from grandparent to grandchild and you have a deeply nested trickle down structure.

Children are unpredictable.  They change over time.  Children aren't comparable.  Children nullify PureRenderMixin.  They're expensive.

Independent children: get to the point where you're not relying on your parent to pass on everything you need.  Aggressive insulation between parent and child.

**Containers vs. Components**

Container does data fetching and renders its corresponding sub component. Regular components render UI and are data agnostic.

Container would be where you might subscribe to a store.  Container is a data layer.  And when you're using it you can get to the point where you have insulation from the child component.  Containers don't have children and shouldn't have any props ideally.

If someone else wants to use a component with different data they can just wrap it in their own container.  And then the components can be put in a component library environment with dummy data.

In the data table example, every cell is its own application.

**Basic conncepts for optimization**

1. Purity: use shouldComponentUpdate and PureREnderMixin to prevent needless rerenders.
2. Data Comparability: use highly comparable data (immutability)
3. Loose Coupling (Use for both maintainability and performance)
4. Children (are expensive and should exercise independence)

**<FixedDataTable/>**

Open sourcing today.  http://facebook.github.io/fixed-data-table/ | https://github.com/facebook/fixed-data-table/