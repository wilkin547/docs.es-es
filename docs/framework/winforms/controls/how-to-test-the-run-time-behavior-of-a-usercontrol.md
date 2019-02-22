---
title: Procedimiento Probar el comportamiento de tiempo de ejecución de una clase UserControl
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 06f2320648bd8fee3465ea1672be886293667879
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664424"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Filtrar Probar el comportamiento de tiempo de ejecución de una clase UserControl
Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución. Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento es un problema. Una forma más rápida y sencilla es usar el **UserControl Test Container** proporcionadas por Visual Studio. Este contenedor de prueba se inicia directamente desde un proyecto de biblioteca de control de Windows.  
  
> [!IMPORTANT]
>  Para el contenedor de prueba cargar su <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
> [!NOTE]
>  No se puede probar un control Visual C++ utilizando el **UserControl Test Container**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Para probar el comportamiento de tiempo de ejecución de una clase UserControl  
  
1.  Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample**. Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).  
  
2.  En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.  
  
3.  Presione F5 para compilar el proyecto y ejecutar el **UserControl Test Container**. El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.  
  
4.  Seleccione el <xref:System.Windows.Forms.Control.BackColor%2A> las propiedades mostradas en la <xref:System.Windows.Forms.PropertyGrid> control a la derecha de la **Preview** panel. Cambie su valor a `ControlDark`. Observe que el control cambia a un color más oscuro. Pruebe a cambiar otros valores de propiedad y observar el efecto en el control.  
  
5.  Haga clic en el **Control de usuario Dock Fill** casilla de verificación siguiente el **Preview** panel. Observe que el control cambia de tamaño para rellenar el panel. Cambiar el tamaño del contenedor de prueba y observe que el control cambia de tamaño con el panel.  
  
6.  Cierre el contenedor de prueba.  
  
7.  Agregue otro control de usuario para el **TestContainerExample** proyecto. Para obtener más detalles, vea [Cómo: Agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).  
  
8.  En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.  
  
9. Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.  
  
10. Haga clic en el **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.  
  
## <a name="testing-user-controls-from-another-project"></a>Probar los controles de usuario desde otro proyecto  
 Puede probar los controles de usuario desde otros proyectos en el contenedor de prueba del proyecto actual.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Para probar los controles de usuario desde otro proyecto  
  
1.  Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample2**. Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).  
  
2.  En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.  
  
3.  Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba. El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.  
  
4.  Haga clic en el **carga** botón.  
  
5.  En el **abierto** diálogo cuadro, vaya a **TestContainerExample**.dll, que basa en el procedimiento anterior. Seleccione **TestContainerExample**.dll y haga clic en el **abierto** botón para cargar los controles de usuario  
  
6.  Use la **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario desde el **TestContainerExample** proyecto.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.UserControl>
- [Cómo: Crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)
- [Tutorial: Crear un Control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Tutorial: Crear un Control compuesto con VisualC#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
