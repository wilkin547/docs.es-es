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
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180206"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedimiento Probar el comportamiento en tiempo de ejecución de un control UserControl

Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución. Puede crear un proyecto de aplicación basado en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento no es práctico. Una manera más rápida y sencilla es usar el **contenedor de pruebas de UserControl** que proporciona Visual Studio. Este contenedor de prueba se inicia directamente desde el proyecto de biblioteca de controles de Windows.

> [!IMPORTANT]
> Para que el contenedor de prueba cargue el <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.

> [!NOTE]
> No se C++ puede probar un control visual mediante **UserControl Test Container**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Probar el comportamiento en tiempo de ejecución de un control UserControl

1. En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **TestContainerExample**.

2. En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.Label> desde el **cuadro de herramientas** hasta la superficie de diseño del control.

3. Presione <kbd>F5</kbd> para compilar el proyecto y ejecutar **UserControl Test Container**. El contenedor de prueba aparece con el <xref:System.Windows.Forms.UserControl> en el panel de **vista previa** .

4. Seleccione la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> que se muestra en el control <xref:System.Windows.Forms.PropertyGrid> a la derecha del panel de **vista previa** . Cambie su valor a **ControlDark**. Observe que el control cambia a un color más oscuro. Intente cambiar otros valores de propiedad y observe el efecto en el control.

5. En el panel de **vista previa** , haga clic en la casilla **control de usuario acoplar relleno** . Observe que el control cambia de tamaño para rellenar el panel. Cambie el tamaño del contenedor de pruebas y observe que se cambia el tamaño del control con el panel.

6. Cierre el contenedor de prueba.

7. Agregue otro control de usuario al proyecto **TestContainerExample** .

8. En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta la superficie de diseño del control.

9. Presione <kbd>F5</kbd> para compilar el proyecto y ejecutar el contenedor de prueba.

10. Haga clic en **seleccionar control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.

## <a name="test-user-controls-from-another-project"></a>Probar controles de usuario desde otro proyecto

Puede probar los controles de usuario de otros proyectos en el contenedor de pruebas del proyecto actual.

1. En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **TestContainerExample2**.

2. En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.RadioButton> desde el **cuadro de herramientas** hasta la superficie de diseño del control.

3. Presione <kbd>F5</kbd> para compilar el proyecto y ejecutar el contenedor de prueba. El contenedor de prueba aparece con el <xref:System.Windows.Forms.UserControl> en el panel de **vista previa** .

4. Haga clic en el botón **cargar** .

5. En el cuadro de diálogo **abrir** , vaya a *TestContainerExample. dll*, que creó en el procedimiento anterior. Seleccione *TestContainerExample. dll* y haga clic en el botón **abrir** para cargar los controles de usuario.

6. Use el **control de usuario Select** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario del proyecto **TestContainerExample** .

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.UserControl>
- [Cómo: Crear controles compuestos @ no__t-0
- [Tutorial: Crear un control compuesto @ no__t-0
- [Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
