---
title: "C&#243;mo: Acoplar controles en formularios Windows Forms | Microsoft Docs"
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
  - "controles [Windows Forms], acoplar"
  - "Dock (propiedad)"
  - "aplicaciones de tipo Explorador, crear"
  - "controles de Windows Forms, rellenar el área de cliente"
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Acoplar controles en formularios Windows Forms
Puede acoplar los controles a los bordes del formulario o hacer que llenen el contenedor del control \(un formulario o un control contenedor\).  Por ejemplo, el Explorador de Windows acopla su control <xref:System.Windows.Forms.TreeView> en el lado izquierdo de la ventana y su control <xref:System.Windows.Forms.ListView> en el lado derecho.  Utilice la propiedad <xref:System.Windows.Forms.Control.Dock%2A> para todos los controles visibles de formularios Windows Forms para definir el modo de acoplamiento.  
  
> [!NOTE]
>  Los controles se acoplan en orden z inverso.  
  
 La propiedad <xref:System.Windows.Forms.Control.Dock%2A> interactúa con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.  Para obtener más información, consulte [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### Para acoplar un control  
  
1.  Seleccione el control que desee acoplar.  
  
2.  En la Ventana Propiedades, haga clic en la flecha situada a la derecha de la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.  
  
     Se mostrará un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.  
  
3.  Haga clic en el botón que representa el borde del formulario al que desea acoplar el control.  Para llenar el contenido del formulario del control o del control contenedor, haga clic en el cuadro central.  Haga clic en **\(ninguno\)** para deshabilitar el acoplamiento.  
  
     El tamaño del control cambiará automáticamente para ajustarse a los límites del borde acoplado.  
  
    > [!NOTE]
    >  Los controles heredados deben estar protegidos \(`Protected`\) para que se puedan acoplar.  Para cambiar el nivel de acceso de un control, establezca su propiedad **Modifier** en la ventana Propiedades.  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [Cómo: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Cómo: Delimitar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)