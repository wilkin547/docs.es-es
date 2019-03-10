---
title: Filtrar Crear una actividad
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 271f26888e8b140b64464f5c9c4eabb7170afe05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709023"
---
# <a name="how-to-create-an-activity"></a>Filtrar Crear una actividad

Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)]. La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades. Este tema muestra cómo crear dos actividades. La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución. La implementación de la segunda actividad se define mediante otras actividades. Estas actividades se usan en los siguientes pasos del tutorial.

> [!NOTE]
> Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="create-the-activity-library-project"></a>Crear el proyecto de biblioteca de actividades

1.  Abra Visual Studio y elija **New** > **proyecto** desde el **archivo** menú.

2.  En el **nuevo proyecto** cuadro de diálogo, en el **instalado** categoría, seleccione **Visual C#** > **flujo de trabajo** (o **Visual Basic** > **flujo de trabajo**).

    > [!NOTE]
    > Si no ve el **flujo de trabajo** categoría de plantilla, es posible que deba instalar el **Windows Workflow Foundation** componente de Visual Studio. Elija la **abrir Visual Studio Installer** vínculo en el lado izquierdo de la **nuevo proyecto** cuadro de diálogo. En el instalador de Visual Studio, seleccione el **componentes individuales** ficha. A continuación, en el **las actividades de desarrollo** categoría, seleccione el **Windows Workflow Foundation** componente. Elija **modificar** para instalar el componente.

3. Seleccione el **biblioteca de actividades** plantilla de proyecto. Tipo `NumberGuessWorkflowActivities` en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.

4.  Haga clic en **Activity1.xaml** en **el Explorador de soluciones** y elija **eliminar**. Haga clic en **Aceptar** para confirmar.

## <a name="create-the-readint-activity"></a>Creación de la actividad ReadInt

1.  Elija **Agregar nuevo elemento** desde el **proyecto** menú.

2.  En el **instalado** > **elementos comunes** nodo, seleccione **flujo de trabajo**. Seleccione **actividad Code** desde el **flujo de trabajo** lista.

3.  Tipo `ReadInt` en el **nombre** cuadro y, a continuación, haga clic en **agregar**.

4.  Reemplace la definición de `ReadInt` existente con la siguiente.

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código. <xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.

## <a name="create-the-prompt-activity"></a>Creación de la actividad Prompt

1.  Presione **Ctrl**+**MAYÚS**+**B** para compilar el proyecto. La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.

2.  Elija **Agregar nuevo elemento** desde el **proyecto** menú.

3.  En el **instalado** > **elementos comunes** nodo, seleccione **flujo de trabajo**. Seleccione **actividad** desde el **flujo de trabajo** lista.

4.  Tipo `Prompt` en el **nombre** cuadro y, a continuación, haga clic en **agregar**.

5.  Haga doble clic en **Prompt.xaml** en **el Explorador de soluciones** para mostrarlo en el diseñador, si aún no se muestra.

6.  Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para mostrar el **argumentos** panel.

7.  Haga clic en **crear argumento**.

8.  Tipo `BookmarkName` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione **ENTRAR** para guardar el argumento.

9. Haga clic en **crear argumento**.

10. Tipo `Result` en el **nombre** cuadro situado debajo de la recién agregada `BookmarkName` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione **ENTRAR**.

11. Haga clic en **crear argumento**.

12. Tipo `Text` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione **ENTRAR** para guardar el argumento.

     Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.

13. Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **argumentos** panel.

14. Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiqueta de la **Prompt** Diseñador de actividad.

    > [!TIP]
    > Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.

15. Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiqueta de la **Secuencia** actividad.

16. Enlazar el **texto** argumento de la **WriteLine** actividad a la **texto** argumento de la **Prompt** actividad escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro el **propiedades** ventana y, a continuación, presione el **ficha** clave de dos veces. Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad. Esta propiedad también puede establecerse escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro en la propia actividad.

    > [!TIP]
    > Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.

17. Arrastre un **ReadInt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad para que siga a la **WriteLine** actividad.

18. Enlazar el **BookmarkName** argumento de la **ReadInt** actividad a la **BookmarkName** argumento de la **Prompt** actividad escribiendo `BookmarkName` en el **escriba una expresión de VB** cuadro a la derecha de la **BookmarkName** argumento en el **ventana propiedades**y, a continuación, presione el **Ficha** dos veces para cerrar la ventana de IntelliSense lista de miembros y guardar la propiedad de clave.

19. Enlazar el **resultado** argumento de la **ReadInt** actividad a la **resultado** argumento de la **Prompt** actividad escribiendo `Result` en el **escriba una expresión de VB** cuadro a la derecha de la **resultado** argumento en el **ventana propiedades**y, a continuación, presione el **ficha** clave dos veces.

20. Presione **Ctrl**+**MAYÚS**+**B** para compilar la solución.

## <a name="next-steps"></a>Pasos siguientes

Para obtener instrucciones sobre cómo crear un flujo de trabajo mediante el uso de estas actividades, vea el paso siguiente en el tutorial, [Cómo: crear un flujo de trabajo](how-to-create-a-workflow.md).

## <a name="see-also"></a>Vea también

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [Diseño e implementación de actividades personalizadas](designing-and-implementing-custom-activities.md)
- [Tutorial de introducción](getting-started-tutorial.md)
- [Cómo: Crear un flujo de trabajo](how-to-create-a-workflow.md)
- [Uso de ExpressionTextBox en un diseñador de actividad personalizado](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)