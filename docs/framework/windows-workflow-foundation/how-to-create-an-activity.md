---
title: 'Cómo: Crear una actividad'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: deb1b6ca5c6fc996a015e32dd5e0c7b9bd6530fa
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137608"
---
# <a name="how-to-create-an-activity"></a>Cómo: Crear una actividad
Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)]. La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades. Este tema muestra cómo crear dos actividades. La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución. La implementación de la segunda actividad se define mediante otras actividades. Estas actividades se usan en los siguientes pasos del tutorial.  
  
> [!NOTE]
>  Para descargar una versión completada del tutorial, consulte [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-activity-library-project"></a>Para crear el proyecto de biblioteca de actividades  
  
1.  Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y elija **New**, **proyecto** desde el **archivo** menú.  
  
2.  Expanda el **otros tipos de proyectos** nodo en el **instalado**, **plantillas** lista y seleccione **soluciones de Visual Studio**.  
  
3.  Seleccione **solución en blanco** desde el **soluciones de Visual Studio** lista. Asegúrese de que se haya seleccionado **.NET Framework 4.5** en la lista desplegable correspondiente a la versión de .NET Framework. Tipo `WF45GettingStartedTutorial` en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.  
  
4.  Haga clic en **WF45GettingStartedTutorial** en **el Explorador de soluciones** y elija **agregar**, **nuevo proyecto**.  
  
    > [!TIP]
    >  Si la ventana **Explorador de soluciones** no se muestra, seleccione **Explorador de soluciones** en el menú **Ver** .  
  
5.  En el nodo **Instalado** , seleccione **Visual C#**, **Flujo de trabajo** (o **Visual Basic**, **Flujo de trabajo**). Asegúrese de que **.NET Framework 4.5** está seleccionado en el [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] lista desplegable de versión. Seleccione **biblioteca de actividades** desde el **flujo de trabajo** lista. Tipo `NumberGuessWorkflowActivities` en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  En función del lenguaje de programación que se configure como lenguaje principal en Visual Studio, el nodo **Visual C#** o **Visual Basic** puede estar bajo el nodo **Otros lenguajes** en el nodo **Instalado** .  
  
6.  Haga clic en **Activity1.xaml** en **el Explorador de soluciones** y elija **eliminar**. Haga clic en **Aceptar** para confirmar.  
  
### <a name="to-create-the-readint-activity"></a>Para crear la actividad ReadInt  
  
1.  Elija **Agregar nuevo elemento** desde el **proyecto** menú.  
  
2.  En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**. Seleccione **actividad Code** desde el **flujo de trabajo** lista.  
  
3.  Tipo `ReadInt` en el **nombre** cuadro y, a continuación, haga clic en **agregar**.  
  
4.  Reemplace la definición de `ReadInt` existente con la siguiente.  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código. <xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.  
  
### <a name="to-create-the-prompt-activity"></a>Para crear la actividad Prompt  
  
1.  Presione Ctrl+Mayús+B para compilar el proyecto. La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.  
  
2.  Elija **Agregar nuevo elemento** desde el **proyecto** menú.  
  
3.  En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**. Seleccione **actividad** desde el **flujo de trabajo** lista.  
  
4.  Tipo `Prompt` en el **nombre** cuadro y, a continuación, haga clic en **agregar**.  
  
5.  Haga doble clic en **Prompt.xaml** en **el Explorador de soluciones** para mostrarlo en el diseñador, si aún no se muestra.  
  
6.  Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para mostrar el **argumentos** panel.  
  
7.  Haga clic en **crear argumento**.  
  
8.  Tipo `BookmarkName` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
9. Haga clic en **crear argumento**.  
  
10. Tipo `Result` en el **nombre** cuadro situado debajo de la recién agregada `BookmarkName` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR.  
  
11. Haga clic en **crear argumento**.  
  
12. Tipo `Text` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
     Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.  
  
13. Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **argumentos** panel.  
  
14. Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiqueta de la **Prompt** Diseñador de actividad.  
  
    > [!TIP]
    >  Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.  
  
15. Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiqueta de la **Secuencia** actividad.  
  
16. Enlazar el **texto** argumento de la **WriteLine** actividad a la **texto** argumento de la **Prompt** actividad escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro el **propiedades** ventana y, a continuación, presione la PESTAÑA clave dos veces. Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad. Esta propiedad también puede establecerse escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro en la propia actividad.  
  
    > [!TIP]
    >  Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.  
  
17. Arrastre un **ReadInt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad para que siga a la **WriteLine** actividad.  
  
18. Enlazar el **BookmarkName** argumento de la **ReadInt** actividad a la **BookmarkName** argumento de la **Prompt** actividad escribiendo `BookmarkName` en el **escriba una expresión de VB** cuadro a la derecha de la **BookmarkName** argumento en el **ventana propiedades**y, a continuación, presione la tecla TAB dos tiempo de espera para cerrar la ventana de IntelliSense lista de miembros y guardar la propiedad.  
  
19. Enlazar el **resultado** argumento de la **ReadInt** actividad a la **resultado** argumento de la **Prompt** actividad escribiendo `Result` en el **escriba una expresión de VB** cuadro a la derecha de la **resultado** argumento en el **ventana propiedades**y, a continuación, presione la tecla TAB dos veces.  
  
20. Presione Ctrl+MAYÚS+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo crear un flujo de trabajo mediante el uso de estas actividades, vea el paso siguiente en el tutorial, [Cómo: crear un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [Diseño e implementación de actividades personalizadas](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Cómo crear un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [Uso de ExpressionTextBox en un diseñador de actividad personalizado](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
