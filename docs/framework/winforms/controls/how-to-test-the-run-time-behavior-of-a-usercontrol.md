---
title: "Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ce4f821a7b964b3ed2e03c795346b47bb88d618
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución
Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución. Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento es un problema. Una manera más rápida y sencilla es usar el **UserControl Test Container** proporcionada por Visual Studio. Este contenedor de prueba se inicia directamente desde el proyecto de biblioteca de controles de Windows.  
  
> [!IMPORTANT]
>  Para el contenedor de prueba cargar su <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!NOTE]
>  No se puede probar un control de Visual C++ mediante el **UserControl Test Container**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Para probar el comportamiento de tiempo de ejecución de un control de usuario  
  
1.  Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample**. Para obtener más información, consulte [plantilla de biblioteca de controles de Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** en la superficie de diseño del control.  
  
3.  Presione F5 para compilar el proyecto y ejecutar el **UserControl Test Container**. El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **vista previa** panel.  
  
4.  Seleccione el <xref:System.Windows.Forms.Control.BackColor%2A> las propiedades mostradas en la <xref:System.Windows.Forms.PropertyGrid> control a la derecha de la **vista previa** panel. Cambie su valor a `ControlDark`. Observe que el control cambia a un color más oscuro. Pruebe a cambiar otros valores de propiedad y observe el efecto en el control.  
  
5.  Haga clic en el **Control de usuario Dock Fill** siguiente casilla de verificación el **vista previa** panel. Observe que el control cambia de tamaño para rellenar el panel. Cambiar el tamaño del contenedor de prueba y observe que el control cambia de tamaño con el panel.  
  
6.  Cierre el contenedor de prueba.  
  
7.  Agregue otro control de usuario para la **TestContainerExample** proyecto. Para obtener más información, consulte [NIB: Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en la superficie de diseño del control.  
  
9. Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.  
  
10. Haga clic en el **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.  
  
## <a name="testing-user-controls-from-another-project"></a>Probar los controles de usuario desde otro proyecto  
 Puede probar los controles de usuario de otros proyectos en el contenedor de prueba del proyecto actual.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Para probar los controles de usuario desde otro proyecto  
  
1.  Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample2**. Para obtener más información, consulte [plantilla de biblioteca de controles de Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> controlar desde la **cuadro de herramientas** en la superficie de diseño del control.  
  
3.  Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba. El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **vista previa** panel.  
  
4.  Haga clic en el **carga** botón.  
  
5.  En el **abiertos** diálogo cuadro, vaya a **TestContainerExample**.dll, que basa en el procedimiento anterior. Seleccione **TestContainerExample**.dll y haga clic en el **abiertos** botón para cargar los controles de usuario  
  
6.  Use la **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario desde el **TestContainerExample** proyecto.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.UserControl>  
 [Cómo: Crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Tutorial: Crear un control compuesto con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Diseñador de controles de usuario](http://msdn.microsoft.com/en-us/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
