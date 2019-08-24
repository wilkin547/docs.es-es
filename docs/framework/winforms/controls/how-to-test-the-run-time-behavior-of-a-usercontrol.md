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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1be79d52be3b5b84938d8548a8f101e965fa9dbb
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015780"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedimiento Probar el comportamiento en tiempo de ejecución de un control UserControl

Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución. Puede crear un proyecto de aplicación basado en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento no es práctico. Una manera más rápida y sencilla es usar el **contenedor de pruebas de UserControl** que proporciona Visual Studio. Este contenedor de prueba se inicia directamente desde el proyecto de biblioteca de controles de Windows.

> [!IMPORTANT]
> Para que el contenedor de prueba cargue <xref:System.Windows.Forms.UserControl>su, el control debe tener al menos un constructor público.

> [!NOTE]
> No se C++ puede probar un control visual mediante **UserControl Test Container**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Probar el comportamiento en tiempo de ejecución de un control UserControl

1. En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **TestContainerExample**.

2. En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> control desde el **cuadro de herramientas** hasta la superficie de diseño del control.

3. Presione **F5** para compilar el proyecto y ejecutar **UserControl Test Container**. El contenedor <xref:System.Windows.Forms.UserControl> de prueba aparece con en el panel de **vista previa** .

4. Seleccione la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad que se muestra <xref:System.Windows.Forms.PropertyGrid> en el control, a la derecha del panel de **vista previa** . Cambie su valor a **ControlDark**. Observe que el control cambia a un color más oscuro. Intente cambiar otros valores de propiedad y observe el efecto en el control.

5. En el panel de **vista previa** , haga clic en la casilla **control de usuario acoplar relleno** . Observe que el control cambia de tamaño para rellenar el panel. Cambie el tamaño del contenedor de pruebas y observe que se cambia el tamaño del control con el panel.

6. Cierre el contenedor de prueba.

7. Agregue otro control de usuario al proyecto **TestContainerExample** .

8. En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> control desde el **cuadro de herramientas** hasta la superficie de diseño del control.

9. Presione **F5** para compilar el proyecto y ejecutar el contenedor de prueba.

10. Haga clic en el<xref:System.Windows.Forms.ComboBox> **control Seleccionar usuario** para cambiar entre los dos controles de usuario.

## <a name="test-user-controls-from-another-project"></a>Probar controles de usuario desde otro proyecto

Puede probar los controles de usuario de otros proyectos en el contenedor de pruebas del proyecto actual.

1. En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **TestContainerExample2**.

2. En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> control desde el **cuadro de herramientas** hasta la superficie de diseño del control.

3. Presione **F5** para compilar el proyecto y ejecutar el contenedor de prueba. El contenedor <xref:System.Windows.Forms.UserControl> de prueba aparece con en el panel de **vista previa** .

4. Haga clic en el botón **cargar** .

5. En el cuadro de diálogo **abrir** , vaya a **TestContainerExample**. dll, que creó en el procedimiento anterior. Seleccione **TestContainerExample**. dll y haga clic en el botón **abrir** para cargar los controles de usuario.

6. Use<xref:System.Windows.Forms.ComboBox> el **control Seleccionar usuario** para cambiar entre los dos controles de usuario del proyecto **TestContainerExample** .

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- [Cómo: Crear controles compuestos](how-to-author-composite-controls.md)
- [Tutorial: Crear un control compuesto](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
