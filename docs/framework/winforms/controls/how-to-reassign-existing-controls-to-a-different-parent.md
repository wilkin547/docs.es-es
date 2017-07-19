---
title: "C&#243;mo: Reasignar controles existentes en un elemento primario diferente | Microsoft Docs"
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
  - "controles contenedor, formularios Windows Forms"
  - "diseño [formularios Windows Forms], cambiar tamaño"
  - "diseño [formularios Windows Forms], controles secundarios"
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Reasignar controles existentes en un elemento primario diferente
Puede asignar controles que existen en el formulario a un nuevo control contenedor.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**. Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para reasignar los controles existentes en un elemento primario diferente  
  
1.  Arrastre tres controles <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.  
  
     Colóquelos cerca entre sí, pero sin alinearlos.  
  
2.  En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
     No arrastre el icono hasta el formulario.  
  
3.  Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button>.  
  
     Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.  
  
4.  Haga clic y mantenga presionado el botón del mouse.  
  
5.  Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
6.  Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button>.  
  
7.  Suelte el botón del mouse.  
  
     Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)