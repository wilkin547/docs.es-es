---
title: Procedimiento para comprobar el comportamiento de UserControl en tiempo de ejecución
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211701"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedimiento Probar el comportamiento de tiempo de ejecución de una clase UserControl

Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución. Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento es un problema. Una forma más rápida y sencilla es usar el **UserControl Test Container** proporcionadas por Visual Studio. Este contenedor de prueba se inicia directamente desde un proyecto de biblioteca de control de Windows.

> [!IMPORTANT]
> Para el contenedor de prueba cargar su <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.

> [!NOTE]
> No se puede probar un control Visual C++ utilizando el **UserControl Test Container**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Probar el comportamiento de tiempo de ejecución de una clase UserControl

1. En Visual Studio, cree un proyecto de biblioteca de controles de Windows denominado **TestContainerExample**. Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.

3. Presione **F5** para compilar el proyecto y ejecutar el **UserControl Test Container**. El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.

4. Seleccione el <xref:System.Windows.Forms.Control.BackColor%2A> las propiedades mostradas en la <xref:System.Windows.Forms.PropertyGrid> control a la derecha de la **Preview** panel. Cambie su valor a `ControlDark`. Observe que el control cambia a un color más oscuro. Pruebe a cambiar otros valores de propiedad y observar el efecto en el control.

5. Haga clic en el **Control de usuario Dock Fill** casilla de verificación siguiente el **Preview** panel. Observe que el control cambia de tamaño para rellenar el panel. Cambiar el tamaño del contenedor de prueba y observe que el control cambia de tamaño con el panel.

6. Cierre el contenedor de prueba.

7. Agregue otro control de usuario para el **TestContainerExample** proyecto. Para obtener más detalles, vea [Cómo: Agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).

8. En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.

9. Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.

10. Haga clic en el **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.

## <a name="test-user-controls-from-another-project"></a>Controles de usuario de prueba de otro proyecto

Puede probar los controles de usuario desde otros proyectos en el contenedor de prueba del proyecto actual.

1. Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample2**. Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.

3. Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba. El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.

4. Haga clic en el **carga** botón.

5. En el **abierto** diálogo cuadro, vaya a **TestContainerExample**.dll, que basa en el procedimiento anterior. Seleccione **TestContainerExample**.dll y haga clic en el **abierto** botón para cargar los controles de usuario

6. Use la **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario desde el **TestContainerExample** proyecto.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- [Cómo: Crear controles compuestos](how-to-author-composite-controls.md)
- [Tutorial: Crear un Control compuesto con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Tutorial: Crear un Control compuesto con VisualC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
