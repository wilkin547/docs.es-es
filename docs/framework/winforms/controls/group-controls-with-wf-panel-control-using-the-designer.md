---
title: "C&#243;mo: Agrupar controles con el control Panel de Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "controles [Windows Forms], agrupar"
  - "Panel (control) [Windows Forms], agrupar controles"
  - "controles de Windows Forms, agrupar"
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Agrupar controles con el control Panel de Windows Forms mediante el Dise&#241;ador
Los controles <xref:System.Windows.Forms.Panel> de Windows Forms se utilizan para agrupar otros controles.  Los controles se pueden agrupar por tres motivos:  para agrupar de forma visual los elementos relacionados del formulario con el fin de obtener una interfaz de usuario clara, para agrupar mediante programación, como en el caso de los botones de radio, y para mover los controles como una unidad en tiempo de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un grupo de controles  
  
1.  Arrastre a un formulario un control <xref:System.Windows.Forms.Panel> desde la ficha **Windows Forms** del Cuadro de herramientas.  
  
2.  Agregue otros controles al panel; para ello, dibuje cada control dentro del panel.  
  
     Si tiene controles que desee incluir en un panel, puede seleccionarlos todos, cortarlos al Portapapeles, seleccionar el control <xref:System.Windows.Forms.Panel> y, a continuación, pegarlos en el panel.  También puede arrastrarlos al panel.  
  
3.  \(Opcional\) Si desea agregar un borde a un panel, establezca su propiedad <xref:System.Windows.Forms.BorderStyle>.  Hay tres opciones: <xref:System.Windows.Forms.BorderStyle>, <xref:System.Windows.Forms.BorderStyle> y <xref:System.Windows.Forms.BorderStyle>.  
  
## Vea también  
 [Control Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Cómo: Establecer el fondo de un panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)