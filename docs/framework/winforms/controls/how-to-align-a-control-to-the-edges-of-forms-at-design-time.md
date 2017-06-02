---
title: "C&#243;mo: Alinear un control con los bordes de los formularios en tiempo de dise&#241;o | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], acoplar mediante el diseñador"
  - "Dock (propiedad), alinear controles (mediante el diseñador)"
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Alinear un control con los bordes de los formularios en tiempo de dise&#241;o
Puede alinear un control en los bordes de los formularios estableciendo la <xref:System.Windows.Forms.Control.Dock%2A>.  Esta propiedad designa la ubicación del control en el formulario.  La propiedad <xref:System.Windows.Forms.Control.Dock%2A> se puede establecer en los siguientes valores:  
  
|Configuración|Efecto en un control|  
|-------------------|--------------------------|  
|<xref:System.Windows.Forms.DockStyle>|Lo acopla en la parte inferior del formulario.|  
|<xref:System.Windows.Forms.DockStyle>|Llena todo el espacio restante del formulario.|  
|<xref:System.Windows.Forms.DockStyle>|Lo acopla en el lado izquierdo del formulario.|  
|<xref:System.Windows.Forms.DockStyle>|No lo acopla en ningún sitio y aparece en la ubicación indicada por su <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle>|Lo acopla en el lado derecho del formulario.|  
|<xref:System.Windows.Forms.DockStyle>|Lo acopla en la parte superior del formulario.|  
  
 Estos valores también se pueden establecer en código.  Para obtener más información, vea [Cómo: Alinear un control con los bordes de los formularios](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer la propiedad Dock en su control en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione el control.  
  
2.  En la ventana **Propiedades**, haga clic en el cuadro de lista desplegable junto a la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.  
  
     Se muestra una interfaz gráfica que representa los seis posibles valores de <xref:System.Windows.Forms.Control.Dock%2A>.  
  
3.  Elija el valor apropiado.  
  
4.  El control se acoplará del modo indicado por el valor.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName>   
 [Cómo: Alinear un control con los bordes de los formularios](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Cómo: Delimitar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Cómo: Delimitar y acoplar controles secundarios en un control FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)