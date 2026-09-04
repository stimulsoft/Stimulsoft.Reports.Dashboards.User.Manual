## Events and Data Band

> **Important**
>
> Scripts can be a security risk, so they are disabled in the [Interpretation mode](../../Reports_Designer/Template/Calculation_Mode.md). However, if you are confident in the safety of your scripts, you can use them in the [Compilation mode](../../Reports_Designer/Template/Calculation_Mode.md).


In addition to the events available for all components, the **Data** band provides three special events: **BeginRenderEvent**, **EndRenderEvent**, and **RenderingEvent**. These events are available because the **Data** band is rendered once for each data row in the specified data source. For example, if the data source contains 10 rows, the **Data** band is rendered 10 times. The **BeginRenderEvent** event occurs before the **Data** band begins rendering, before any data rows have been printed. You can use this event to initialize data or variables and perform other required actions. The **EndRenderEvent** event occurs after the **Data** band has finished rendering, when all data rows have been printed. It is typically used to process data and calculation results. Finally, the **RenderingEvent** event occurs when an individual data row is being rendered. It is triggered before the **Data** band is printed. If the data source contains 10 rows, the **RenderingEvent** event is triggered 10 times. To calculate the number of items in the data source, add the following code to the **BeginRenderEvent** event:


Calculate a number of elements in the data source. Write the following code in the **BeginRenderEvent**:


myvariable = 0;


Also it is necessary to create the **myvariable** variable in the data dictionary. Write the following code in the **RenderingEvent**:


myvariable = myvariable + 1;


And the **EndRenderEvent** is not used in this case. As a result of calculation the **myvariable** will store the value that is equal to the number of elements in the data source. To output this value in the **Text** component the following expression will be used:


{myvariable}


Also it is necessary to set the **ProcessAtEnd** property of the **Text** component to **true**. It is necessary to output the calculated value in the **myvariable.**
