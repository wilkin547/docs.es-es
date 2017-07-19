---
title: "Usar la actividad Interop en un flujo de trabajo de .NET Framework 4 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Usar la actividad Interop en un flujo de trabajo de .NET Framework 4
Las actividades creadas con [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] o [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] pueden utilizarse en un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo utilizando el <xref:System.Activities.Statements.Interop> actividad. Este tema proporciona una introducción al uso de la <xref:System.Activities.Statements.Interop> actividad.  
  
> [!NOTE]
>  El <xref:System.Activities.Statements.Interop> actividad no aparecerá en el cuadro de herramientas Diseñador de flujo de trabajo a menos que el proyecto del flujo de trabajo tiene su **.NET Framework de destino** definida en **.Net Framework 4** o posterior.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>Usar la actividad Interop en flujos de trabajo de .NET Framework 4.5  
 En este tema, se crea una biblioteca de actividades de [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] que contiene una actividad `DiscountCalculator`. El `DiscountCalculator` calcula un descuento basado en el importe de compra y consta de un <xref:System.Workflow.Activities.SequenceActivity> que contiene un <xref:System.Workflow.Activities.PolicyActivity>.  
  
> [!NOTE]
>  La [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] actividad que creó en este tema utiliza un <xref:System.Workflow.Activities.PolicyActivity> para implementar la lógica de la actividad. No es necesario utilizar un personalizado [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] actividad o <xref:System.Activities.Statements.Interop> actividad para poder usar reglas en un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo. Para obtener un ejemplo del uso de reglas en un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo sin usar la <xref:System.Activities.Statements.Interop> actividad, consulte la [actividad Policy en .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) ejemplo.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>Para crear el proyecto de la biblioteca de actividades de .NET Framework 3.5  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y seleccione **nuevo** y, a continuación, **proyecto...** desde el **archivo** menú.  
  
2.  Expanda el **otros tipos de proyectos** nodo en el **Plantillas instaladas** panel y seleccione **soluciones de Visual Studio**.  
  
3.  Seleccione **solución en blanco** desde el **soluciones de Visual Studio** lista. Tipo de `PolicyInteropDemo` en el **nombre** y haga clic en **Aceptar**.  
  
4.  Haga clic en **PolicyInteropDemo** en **el Explorador de soluciones** y seleccione **Agregar** y, a continuación, **nuevo proyecto...**.  
  
    > [!TIP]
    >  Si el **el Explorador de soluciones** ventana no está visible, seleccione **el Explorador de soluciones** desde el **vista** menú.  
  
5.  En el **Plantillas instaladas** lista, seleccione **Visual C#** y, a continuación, **flujo de trabajo**. Seleccione **.NET Framework 3.5** desde la lista desplegable de versión de .NET Framework y, a continuación, seleccione **biblioteca de actividades de flujo de trabajo** desde el **plantillas** lista.  
  
6.  Tipo de `PolicyActivityLibrary` en el **nombre** y haga clic en **Aceptar**.  
  
7.  Haga clic en **Activity1.cs** en **el Explorador de soluciones** y seleccione **Eliminar**. Haga clic en **Aceptar** para confirmar.  
  
#### <a name="to-create-the-discountcalculator-activity"></a>Para crear la actividad DiscountCalculator  
  
1.  Haga clic en **PolicyActivityLibrary** en **el Explorador de soluciones** y seleccione **Agregar** y, a continuación, **actividad...**.  
  
2.  Seleccione **Activity (con separación de código)** desde el **elementos de Visual C#** lista. Tipo de `DiscountCalculator` en el **nombre** y haga clic en **Aceptar**.  
  
3.  Haga clic en **DiscountCalculator.xoml** en **el Explorador de soluciones** y seleccione **Ver código**.  
  
4.  Agregue las siguientes propiedades a la clase `DiscountCalculator`.  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  Haga clic en **DiscountCalculator.xoml** en **el Explorador de soluciones** y seleccione **Ver diseñador**.  
  
6.  Arrastre un **directiva** actividad desde la **Windows Workflow v3.0** sección de la **cuadro de herramientas** y colóquelo el **DiscountCalculator** actividad.  
  
    > [!TIP]
    >  Si el **herramientas** ventana no está visible, seleccione **herramientas** desde el **vista** menú.  
  
#### <a name="to-configure-the-rules"></a>Para configurar las reglas  
  
1.  Haga clic en recién agregado **directiva** actividad para seleccionarla, si no está ya seleccionada.  
  
2.  Haga clic en el **RuleSetReference** propiedad en la **propiedades** ventana para seleccionarlo y haga clic en el botón de puntos suspensivos a la derecha de la propiedad.  
  
    > [!TIP]
    >  Si el **propiedades** ventana no está visible, elija **ventana propiedades** desde el **vista** menú.  
  
3.  Seleccione **haga clic en nuevo...**.  
  
4.  Haga clic en **Agregar regla**.  
  
5.  Escriba la siguiente expresión en el **condición** cuadro.  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  Escriba la siguiente expresión en el **acciones Then** cuadro.  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  Haga clic en **Agregar regla**.  
  
8.  Escriba la siguiente expresión en el **condición** cuadro.  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. Escriba la siguiente expresión en el **acciones Then** cuadro.  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. Haga clic en **Agregar regla**.  
  
11. Escriba la siguiente expresión en el **condición** cuadro.  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. Escriba la siguiente expresión en el **acciones Then** cuadro.  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. Escriba la siguiente expresión en el **acciones Else** cuadro.  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. Haga clic en **Aceptar** para cerrar la **Editor de conjunto de reglas** cuadro de diálogo.  
  
15. Asegúrese de que recién creado <xref:System.Workflow.Activities.Rules.RuleSet> está seleccionado en el **nombre** y haga clic en **Aceptar**.  
  
16. Presione Ctrl+MAYÚS+B para compilar la solución.  
  
 Las reglas agregadas a la actividad `DiscountCalculator` en este procedimiento se muestran en el siguiente ejemplo de código.  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 Cuando el <xref:System.Workflow.Activities.PolicyActivity> se ejecuta, estas tres reglas evalúan y modifican la `Subtotal`, `DiscountPercent`, y `Total` valores de propiedad de la `DiscountCalculator` actividad para calcular el descuento deseado.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Usar la actividad DiscountCalculator con la actividad Interop  
 Para usar la `DiscountCalculator` actividad dentro de un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo, el <xref:System.Activities.Statements.Interop> actividad está en uso. En esta sección dos flujos de trabajo se crean, uno con código y otro con el Diseñador de flujo de trabajo, que muestran cómo utilizar el <xref:System.Activities.Statements.Interop> actividad con la `DiscountCalculator` actividad. La misma aplicación host se usa para ambos flujos de trabajo.  
  
#### <a name="to-create-the-host-application"></a>Para crear la aplicación host  
  
1.  Haga clic en **PolicyInteropDemo** en **el Explorador de soluciones** y seleccione **Agregar**, y luego **nuevo proyecto...**.  
  
2.  Asegúrese de que **.NET Framework 4.5** está seleccionado en la lista desplegable de versión de .NET Framework y seleccione  **aplicación de consola de flujos de trabajo** desde el **elementos de Visual C#** lista.  
  
3.  Tipo de `PolicyInteropHost` en el **nombre** y haga clic en **Aceptar**.  
  
4.  Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **propiedades**.  
  
5.  En el **.NET framework de destino** desplegable lista, cambie la selección de **.NET Framework 4 Client Profile** a **.NET Framework 4.5**. Haga clic en **Sí** para confirmar.  
  
6.  Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **Agregar referencia**.  
  
7.  Seleccione **PolicyActivityLibrary** desde el **proyectos** y haga clic en **Aceptar**.  
  
8.  Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **Agregar referencia**.  
  
9. Seleccione **System.Workflow.Activities**, **System.Workflow.ComponentModel**, y, a continuación, **System.Workflow.Runtime** desde el **.NET** y haga clic en **Aceptar**.  
  
10. Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **establecer como proyecto de inicio**.  
  
11. Presione Ctrl+MAYÚS+B para compilar la solución.  
  
### <a name="using-the-interop-activity-in-code"></a>Usar la actividad Interop en el código  
 En este ejemplo, se crea una definición de flujo de trabajo mediante el código que contiene el <xref:System.Activities.Statements.Interop> actividad y la `DiscountCalculator` actividad. Este flujo de trabajo se invoca mediante <xref:System.Activities.WorkflowInvoker> y los resultados de la evaluación de la regla se escriben en la consola mediante un <xref:System.Activities.Statements.WriteLine> actividad.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>Para usar la actividad Interop en código  
  
1.  Haga clic en **Program.cs** en **el Explorador de soluciones** y seleccione **Ver código**.  
  
2.  Agregue la instrucción `using` siguiente en la parte superior del archivo.  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  Quite el contenido del método `Main` y sustitúyalo con el código siguiente:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  Cree un nuevo método en la clase `Program` denominada `CalculateDiscountUsingCodeWorkflow` que contenga el código siguiente.  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  El `Subtotal`, `DiscountPercent`, y `Total` Propiedades de la `DiscountCalculator` actividad se producen como argumentos de la <xref:System.Activities.Statements.Interop> actividad y variables de flujo de trabajo enlazado a local en el <xref:System.Activities.Statements.Interop> la actividad <xref:System.Activities.Statements.Interop.ActivityProperties%2A> colección. `Subtotal` se agrega como un <xref:System.Activities.ArgumentDirection> argumento porque el `Subtotal` datos fluyen en la <xref:System.Activities.Statements.Interop> actividad, y `DiscountPercent` y `Total` se agregan como <xref:System.Activities.ArgumentDirection> argumentos porque sus datos fluyen fuera de la <xref:System.Activities.Statements.Interop> actividad. Tenga en cuenta que los dos <xref:System.Activities.ArgumentDirection> se agregan argumentos con los nombres `DiscountPercentOut` y `TotalOut` para indicar que representan <xref:System.Activities.ArgumentDirection> argumentos. El `DiscountCalculator` tipo se especifica como el <xref:System.Activities.Statements.Interop> la actividad <xref:System.Activities.Statements.Interop.ActivityType%2A>.  
  
5.  Presione CTRL+F5 para compilar y ejecutar la aplicación. Sustituya los valores diferentes para que el valor `Subtotal` pruebe los niveles del descuento diferentes proporcionados por la actividad `DiscountCalculator`.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Usar la actividad Interop en el Diseñador de flujo de trabajo  
 En este ejemplo, use crea un flujo de trabajo con el diseñador de flujo de trabajo. Este flujo de trabajo tiene la misma funcionalidad que el ejemplo anterior, excepto que en lugar de usar un <xref:System.Activities.Statements.WriteLine> actividad para mostrar el descuento, la aplicación host recupera y muestra la información del descuento cuando se completa el flujo de trabajo. Asimismo, en lugar de usar las variables de flujo de trabajo locales para contener los datos, los argumentos se crean en el diseñador de flujo de trabajo y los valores se pasan desde el host cuando se invoca el flujo de trabajo.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>Para hospedar PolicyActivity usando un flujo de trabajo creado por el Diseñador de flujo de trabajo  
  
1.  Haga clic en **Workflow1.xaml** en **el Explorador de soluciones** y seleccione **Eliminar**. Haga clic en **Aceptar** para confirmar.  
  
2.  Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento...**.  
  
3.  Expanda el **elementos de Visual C#** nodo y seleccione **flujo de trabajo**. Seleccione **actividad** desde el **elementos de Visual C#** lista.  
  
4.  Tipo de `DiscountWorkflow` en el **nombre** y haga clic en **Agregar**.  
  
5.  Haga clic en el **argumentos** botón en la esquina inferior izquierda del Diseñador de flujo de trabajo para mostrar el **argumentos** panel.  
  
6.  Haga clic en **crear argumento**.  
  
7.  Tipo `Subtotal` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **doble** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
    > [!NOTE]
    >  Si **doble** no está en el **el tipo de argumento** lista desplegable, seleccione **buscar tipos …**, tipo `System.Double` en el **nombre de tipo** cuadro y haga clic en **Aceptar**.  
  
8.  Haga clic en **crear argumento**.  
  
9. Tipo `DiscountPercent` en el **nombre** cuadro, seleccione **Out** desde el **dirección** lista desplegable, seleccione **doble** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
10. Haga clic en **crear argumento**.  
  
11. Tipo `Total` en el **nombre** cuadro, seleccione **Out** desde el **dirección** lista desplegable, seleccione **doble** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
12. Haga clic en el **argumentos** botón en la esquina inferior izquierda del Diseñador de flujo de trabajo para cerrar la **argumentos** panel.  
  
13. Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquelo en la superficie del Diseñador de flujo de trabajo.  
  
14. Arrastre un **interoperabilidad** actividad desde la **migración** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad.  
  
15. Haga clic en el **interoperabilidad** actividad en la **haga clic en Examinar...** etiqueta, escriba **DiscountCalculator** en el **nombre de tipo** y haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Cuando el <xref:System.Activities.Statements.Interop> actividad se agrega al flujo de trabajo y el `DiscountCalculator` tipo se especifica como su <xref:System.Activities.Statements.Interop.ActivityType%2A>, el <xref:System.Activities.Statements.Interop> actividad expone tres <xref:System.Activities.ArgumentDirection> argumentos y tres <xref:System.Activities.ArgumentDirection> argumentos que representan las tres propiedades públicas de la `DiscountCalculator` actividad. El <xref:System.Activities.ArgumentDirection> argumentos tienen el mismo nombre que las tres propiedades públicas y los tres <xref:System.Activities.ArgumentDirection> argumentos tengan los mismos nombres con **Out** anexado al nombre de propiedad. En los pasos siguientes, los argumentos de flujo de trabajo creados en los pasos anteriores se enlazan a la <xref:System.Activities.Statements.Interop> argumentos de la actividad.  
  
16. Tipo de `DiscountPercent` en el **Escriba una expresión de VB** cuadro a la derecha de la **DiscountPercentOut** propiedad y presione TAB.  
  
17. Tipo de `Subtotal` en el **Escriba una expresión de VB** cuadro a la derecha de la **Subtotal** propiedad y presione TAB.  
  
18. Tipo de `Total` en el **Escriba una expresión de VB** cuadro a la derecha de la **TotalOut** propiedad y presione TAB.  
  
19. Haga clic en **Program.cs** en **el Explorador de soluciones** y seleccione **Ver código**.  
  
20. Agregue la instrucción `using` siguiente en la parte superior del archivo.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. Ponga un comentario sobre la llamada al método `CalculateDiscountInCode` en el método `Main` y agregue el siguiente código.  
  
    > [!NOTE]
    >  Si no siguiera el procedimiento anterior y el código `Main` predeterminado estuviera presente, reemplace el contenido de `Main` con el siguiente código.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. Cree un nuevo método en la clase `Program` denominada `CalculateDiscountUsingDesignerWorkflow` que contenga el código siguiente.  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. Presione CTRL+F5 para compilar y ejecutar la aplicación. Para especificar un importe de `Subtotal` distinto, cambie el valor de `SubtotalValue` en el siguiente código.  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a>Información general de las características de las reglas  
 El motor de reglas de [!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona soporte técnico para procesar reglas según la prioridad con soporte para el encadenamiento delantero. Las reglas se pueden evaluar para un elemento único o para los elementos de una colección. Para ver una información general de reglas e información sobre la funcionalidad específica de reglas, consulte la siguiente tabla.  
  
|Característica de reglas|Documentación|  
|-------------------|-------------------|  
|Información general sobre reglas|[Introducción al motor de reglas de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|RuleSet|[Utilización de RuleSets en flujos de trabajo](http://go.microsoft.com/fwlink/?LinkId=178516) y <xref:System.Workflow.Activities.Rules.RuleSet>|  
|Evaluación de reglas|[Evaluación de reglas en RuleSets](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|Encadenamiento de reglas|[Control de encadenamiento delantero](http://go.microsoft.com/fwlink/?LinkId=178518) y [encadenamiento delantero de reglas](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|Procesamiento de colecciones en reglas|[Procesamiento de colecciones en reglas](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|Usar PolicyActivity|[Uso de la actividad PolicyActivity](http://go.microsoft.com/fwlink/?LinkId=178521) y <xref:System.Workflow.Activities.PolicyActivity>|  
  
 Flujos de trabajo creados en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] no usan todas las características de reglas proporcionadas por [!INCLUDE[wf1](../../../includes/wf1-md.md)], como condiciones de actividad declarativas y las actividades condicionales como el <xref:System.Workflow.Activities.ConditionedActivityGroup> y <xref:System.Workflow.Activities.ReplicatorActivity>. Si es necesario, esta funcionalidad está disponible para flujos de trabajo creados con [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] y [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Guía de migración](../../../docs/framework/windows-workflow-foundation//migration-guidance.md).