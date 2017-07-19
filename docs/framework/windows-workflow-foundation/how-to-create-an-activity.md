---
title: "C&#243;mo: Crear una actividad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# C&#243;mo: Crear una actividad
Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)].La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades.Este tema muestra cómo crear dos actividades.La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución.La implementación de la segunda actividad se define mediante otras actividades.Estas actividades se usan en los siguientes pasos del tutorial.  
  
> [!NOTE]
>  Para descargar una versión completa del tutorial, vea [Windows Workflow Foundation \(WF45\): tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### Para crear el proyecto de biblioteca de actividades  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y elija **Nuevo**, **Proyecto** en el menú **Archivo**.  
  
2.  Expanda el nodo **Otros tipos de proyectos** en la lista **Instalado**, **Plantillas** y seleccione **Soluciones de Visual Studio**.  
  
3.  Seleccione **Solución en blanco** en la lista **Soluciones de Visual Studio**.Asegúrese de que se haya seleccionado **.NET Framework 4.5** en la lista desplegable correspondiente a la versión de .NET Framework.Escriba `WF45GettingStartedTutorial` en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.  
  
4.  Haga clic con el botón secundario en **WF45GettingStartedTutorial** en el **Explorador de soluciones** y elija **Agregar**, **Nuevo proyecto**.  
  
    > [!TIP]
    >  Si la ventana **Explorador de soluciones** no se muestra, seleccione **Explorador de soluciones** en el menú **Ver**.  
  
5.  En el nodo **Instalado**, seleccione **Visual C\#**, **Flujo de trabajo** \(o **Visual Basic**, **Flujo de trabajo**\).Asegúrese de que se haya seleccionado **.NET Framework 4.5** en la lista desplegable correspondiente a la versión de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].Seleccione **Biblioteca de actividad** en la lista **Flujo de trabajo**.Escriba `NumberGuessWorkflowActivities` en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En función del lenguaje de programación que se configure como lenguaje principal en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], el nodo **Visual C\#** o **Visual Basic** puede estar bajo el nodo **Otros lenguajes** del nodo **Instalado**.  
  
6.  Haga clic con el botón secundario en **Activity1.xaml** en el **Explorador de soluciones** y elija **Eliminar**.Haga clic en **Aceptar** para confirmar.  
  
### Para crear la actividad ReadInt  
  
1.  Elija **Agregar nuevo elemento** en el menú **Proyecto**.  
  
2.  En el nodo **Instalado**, **Elementos comunes**, seleccione **Flujo de trabajo**.Seleccione **Actividad de código** en la lista **Flujo de trabajo**.  
  
3.  Escriba `ReadInt` en el cuadro **Nombre** y, a continuación, haga clic en **Agregar**.  
  
4.  Reemplace la definición de `ReadInt` existente con la siguiente.  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código.<xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.  
  
### Para crear la actividad Prompt  
  
1.  Presione Ctrl\+Mayús\+B para compilar el proyecto.La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.  
  
2.  Elija **Agregar nuevo elemento** en el menú **Proyecto**.  
  
3.  En el nodo **Instalado**, **Elementos comunes**, seleccione **Flujo de trabajo**.Seleccione **Actividad** en la lista **Flujo de trabajo**.  
  
4.  Escriba `Prompt` en el cuadro **Nombre** y, a continuación, haga clic en **Agregar**.  
  
5.  Haga doble clic en **Prompt.xaml** en el **Explorador de soluciones** para que se muestre en el diseñador, si aún no aparece.  
  
6.  Haga clic en el botón **Argumentos**, situado en la parte inferior izquierda del diseñador de actividad, para mostrar el panel **Argumentos**.  
  
7.  Haga clic en **Crear argumento**.  
  
8.  Escriba `BookmarkName` en el cuadro **Nombre**, seleccione **Entrada** en la lista desplegable **Dirección**, seleccione **Cadena** en la lista desplegable **Tipo de argumento** y, después, presione Entrar para guardar el argumento.  
  
9. Haga clic en **Crear argumento**.  
  
10. Escriba `Result` en el cuadro **Nombre** que se encuentra debajo del argumento `BookmarkName` recién agregado, seleccione **Salida** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione ENTRAR.  
  
11. Haga clic en **Crear argumento**.  
  
12. Escriba `Text` en el cuadro **Nombre**, seleccione **Entrada** en la lista desplegable **Dirección**, seleccione **Cadena** en la lista desplegable **Tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.  
  
     Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.  
  
13. Haga clic en el botón **Argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Argumentos**.  
  
14. Arrastre una actividad **Sequence** desde la sección **Flujo de control** del **Cuadro de herramientas** y colóquela sobre la etiqueta **Coloque la actividad aquí** del diseñador de actividad **Prompt**.  
  
    > [!TIP]
    >  Si la ventana **Cuadro de herramientas** no se muestra, seleccione **Cuadro de herramientas** en el menú **Ver**.  
  
15. Arrastre una actividad **WriteLine** de la sección **Primitivas** del **Cuadro de herramientas** y colóquela sobre la etiqueta **Coloque la actividad aquí** de la actividad **Sequence**.  
  
16. Enlace el argumento **Text** de la actividad **WriteLine** al argumento **Text** de la actividad **Prompt**; para ello, escriba `Text` en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB** de la ventana **Propiedades** y, a continuación, presione la tecla TAB dos veces.Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad.Esta propiedad también se puede establecer escribiendo `Text` en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB** en la propia actividad.  
  
    > [!TIP]
    >  Si no se muestra la **Ventana Propiedades**, seleccione **Ventana Propiedades** en el menú **Ver**.  
  
17. Arrastre una actividad **ReadInt** de la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga a la actividad **WriteLine**.  
  
18. Enlace el argumento **BookmarkName** de la actividad **ReadInt** al argumento **BookmarkName** de la actividad **Prompt** escribiendo `BookmarkName` en el cuadro **Escriba una expresión de VB** a la derecha del argumento **BookmarkName** en la **Ventana Propiedades** y, a continuación, presione dos veces la tecla TAB para cerrar la ventana de lista de miembros de IntelliSense y guarde la propiedad.  
  
19. Enlace el argumento **Result** de la actividad **ReadInt** al argumento **Result** de la actividad **Prompt** escribiendo `Result` en el cuadro **Escriba una expresión de VB** a la derecha del argumento **Result** en la **Ventana Propiedades** y, a continuación, presione la tecla TAB dos veces.  
  
20. Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo crear un flujo de trabajo usando estas actividades, vea el siguiente paso del tutorial, [Cómo: Crear flujos de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md).  
  
## Vea también  
 <xref:System.Activities.CodeActivity>   
 <xref:System.Activities.NativeActivity%601>   
 [Diseñar e implementar actividades personalizadas](../../../docs/framework/windows-workflow-foundation//designing-and-implementing-custom-activities.md)   
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Cómo: Crear flujos de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md)   
 [Uso de la ExpressionTextBox en un diseñador de actividad personalizado](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)