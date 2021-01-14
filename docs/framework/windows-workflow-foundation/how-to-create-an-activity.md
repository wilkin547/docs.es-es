---
title: Procedimiento para crear una actividad
description: 'En este artículo se muestra cómo crear dos actividades en Workflow Foundation: una que usa código para implementar su lógica y otra definida mediante otras actividades.'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: c7610d8612eb944afa9c23e1bf2abceeb3a6d38b
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190772"
---
# <a name="how-to-create-an-activity"></a>Procedimiento para crear una actividad

Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)]. La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades. Este tema muestra cómo crear dos actividades. La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución. La implementación de la segunda actividad se define mediante otras actividades. Estas actividades se usan en los siguientes pasos del tutorial.

## <a name="create-the-activity-library-project"></a>Crear el proyecto de biblioteca de actividades

1. Abra Visual Studio y elija **nuevo**  >  **proyecto** en el menú **archivo** .

2. En el cuadro de diálogo **nuevo proyecto** , en la categoría **instalado** , seleccione flujo de trabajo de **Visual C#**  >   (o **Visual Basic**  >  **flujo de trabajo**).

    > [!NOTE]
    > Si no ve la categoría de la plantilla de **flujo de trabajo** , es posible que deba instalar el componente de **Windows Workflow Foundation** de Visual Studio. Elija el vínculo **abrir instalador de Visual Studio** en el lado izquierdo del cuadro de diálogo **nuevo proyecto** . En Instalador de Visual Studio, seleccione la pestaña **componentes individuales** . A continuación, en la categoría **actividades de desarrollo** , seleccione el componente **Windows Workflow Foundation** . Elija **modificar** para instalar el componente.

3. Seleccione la plantilla de proyecto **biblioteca de actividades** . Escriba `NumberGuessWorkflowActivities` en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.

4. Haga clic con el botón secundario en **Activity1.xaml** en el **Explorador de soluciones** y elija **Eliminar**. Haga clic en **ACEPTAR** para continuar.

## <a name="create-the-readint-activity"></a>Crear la actividad ReadInt

1. Elija **Agregar nuevo elemento** en el menú **proyecto** .

2. En el   >  nodo **elementos comunes** instalados, seleccione **flujo de trabajo**. Seleccione **actividad de código** en la lista **flujo de trabajo** .

3. Escriba `ReadInt` en el cuadro **Nombre** y, a continuación, haga clic en **Agregar**.

4. Reemplace la definición de `ReadInt` existente con la siguiente.

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código. <xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.

## <a name="create-the-prompt-activity"></a>Crear la actividad prompt

1. Presione **Ctrl** + **MAYÚS** + **B** para compilar el proyecto. La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.

2. Elija **Agregar nuevo elemento** en el menú **proyecto** .

3. En el   >  nodo **elementos comunes** instalados, seleccione **flujo de trabajo**. Seleccione **Actividad** en la lista **Flujo de trabajo**.

4. Escriba `Prompt` en el cuadro **Nombre** y, a continuación, haga clic en **Agregar**.

5. Haga doble clic en **prompt. Xaml** en **Explorador de soluciones** para mostrarlo en el diseñador si aún no se muestra.

6. Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para mostrar el panel **Argumentos**.

7. Haga clic en **Crear argumento**.

8. Escriba `BookmarkName` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **cadena** en la lista desplegable **tipo de argumento** y, a continuación, presione **entrar** para guardar el argumento.

9. Haga clic en **Crear argumento**.

10. Escriba `Result` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `BookmarkName` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione **entrar**.

11. Haga clic en **Crear argumento**.

12. Escriba `Text` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **cadena** en la lista desplegable **tipo de argumento** y, a continuación, presione **entrar** para guardar el argumento.

     Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.

13. Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.

14. Arrastre una actividad **Sequence** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** del diseñador de actividad **prompt** .

    > [!TIP]
    > Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.

15. Arrastre una **actividad WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** de la actividad **Sequence** .

16. Enlace el argumento de **texto** de la actividad **WriteLine** al argumento de **texto** de la actividad **prompt** escribiendo `Text` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** en la ventana **propiedades** y, a continuación, presione la tecla **Tab** dos veces. Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad. Esta propiedad también se puede establecer escribiendo `Text` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** en la propia actividad.

    > [!TIP]
    > Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .

17. Arrastre una actividad **ReadInt** desde la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga la actividad **WriteLine** .

18. Enlace el **argumento bookmarkname** de la **actividad ReadInt** al argumento **bookmarkname** de la actividad **prompt** escribiendo `BookmarkName` en el cuadro **Escriba una expresión de VB** a la derecha del argumento **bookmarkname** en la **ventana Propiedades** y, a continuación, presione la tecla **Tab** dos veces para cerrar la ventana de lista de miembros de IntelliSense y guardar la propiedad.

19. Enlace el argumento **result** de la **actividad ReadInt** al argumento **result** de la actividad **prompt** escribiendo `Result` en el cuadro **Escriba una expresión de VB** a la derecha del argumento **result** en la **ventana Propiedades** y, a continuación, presione la tecla **Tab** dos veces.

20. Presione **Ctrl** + **MAYÚS** + **B** para compilar la solución.

## <a name="next-steps"></a>Pasos siguientes

Para obtener instrucciones sobre cómo crear un flujo de trabajo mediante estas actividades, vea el siguiente paso del tutorial, [Cómo: crear un flujo de trabajo](how-to-create-a-workflow.md).

## <a name="see-also"></a>Consulta también

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [Diseñar e implementar actividades personalizadas](designing-and-implementing-custom-activities.md)
- [Tutorial de introducción](getting-started-tutorial.md)
- [Procedimiento para crear un flujo de trabajo](how-to-create-a-workflow.md)
- [Uso de la ExpressionTextBox en un diseñador de actividad personalizado](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
