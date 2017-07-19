---
title: "C&#243;mo: Comprobar el comportamiento de un control de usuario en tiempo de ejecuci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles compuestos, pruebas"
  - "controles de usuario [Windows Forms], pruebas"
  - "UserControl (clase), comportamiento en tiempo de ejecución"
  - "UserControl (clase), pruebas"
  - "UserControl Test Container"
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Comprobar el comportamiento de un control de usuario en tiempo de ejecuci&#243;n
Cuando desarrolla un control <xref:System.Windows.Forms.UserControl>, tiene que probar su comportamiento en tiempo de ejecución.  Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento no resulta muy práctico.  Una manera más rápida y más fácil es utilizar el **UserControl Test Container** proporcionado por Visual Studio.  Este contenedor de prueba se inicia directamente desde el proyecto de Biblioteca de controles de Windows.  
  
> [!IMPORTANT]
>  Para que el contenedor de prueba cargue <xref:System.Windows.Forms.UserControl>, el control debe tener por lo menos un constructor público.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!NOTE]
>  Un control de Visual C\+\+ no se puede probar con **UserControl Test Container**.  
  
### Para probar el comportamiento en tiempo de ejecución de UserControl  
  
1.  Cree un proyecto de Biblioteca de controles de Windows denominado TestContainerExample.  Para obtener información detallada, vea [Windows Control Library Template](http://msdn.microsoft.com/es-es/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.Label> desde el **Cuadro de herramientas** a la superficie de diseño de control.  
  
3.  Presione F5 para compilar el proyecto y ejecutar el **UserControl Test Container**.  El contenedor de prueba aparece con <xref:System.Windows.Forms.UserControl> en el panel **Vista previa**.  
  
4.  Seleccione la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> mostrada en el control <xref:System.Windows.Forms.PropertyGrid> situado a la derecha del panel **Vista previa**.  Cambie su valor a `ControlDark`.  Observe que el control cambia a un color más oscuro.  Pruebe a cambiar otros valores de propiedad y observar el efecto en el control.  
  
5.  Haga clic en la casilla **Control de usuario Dock Fill** debajo del panel **Vista previa**.  Observe que se cambia el tamaño del control para rellenar el panel.  Cambie el tamaño del contenedor de prueba y observe que el tamaño del control cambia con el panel.  
  
6.  Cierre el contenedor de prueba.  
  
7.  Agregue otro control de usuario al proyecto TestContainerExample.  Para obtener información detallada, vea [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/es-es/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** a la superficie de diseño de control.  
  
9. Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.  
  
10. Haga clic en **Seleccionar control de usuario** de <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.  
  
## Probar los controles de usuario desde otro proyecto  
 Puede probar los controles de usuario desde otros proyectos en el contenedor de prueba de su proyecto actual.  
  
#### Para probar los controles de usuario desde otro proyecto  
  
1.  Cree un proyecto de Biblioteca de controles de Windows denominado TestContainerExample2.  Para obtener información detallada, vea [Windows Control Library Template](http://msdn.microsoft.com/es-es/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.RadioButton> desde el **Cuadro de herramientas** a la superficie de diseño de control.  
  
3.  Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.  El contenedor de prueba aparece con <xref:System.Windows.Forms.UserControl> en el panel **Vista previa**.  
  
4.  Haga clic en el botón **Cargar**.  
  
5.  En el cuadro de diálogo **Abrir**, navegue hasta TestContainerExample.dll, que compiló en el procedimiento anterior.  Seleccione TestContainerExample.dll y haga clic en el botón **Abrir** para cargar los controles de usuario  
  
6.  Use el <xref:System.Windows.Forms.ComboBox> **Seleccionar control de usuario** para alternar entre los dos controles de usuario del proyecto TestContainerExample.  
  
## Vea también  
 <xref:System.Windows.Forms.UserControl>   
 [Cómo: Crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)   
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [Tutorial: Crear un control compuesto con Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)   
 [User Control Designer](http://msdn.microsoft.com/es-es/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)