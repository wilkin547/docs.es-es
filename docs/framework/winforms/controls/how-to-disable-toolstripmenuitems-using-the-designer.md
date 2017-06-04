---
title: "C&#243;mo: Deshabilitar ToolStripMenuItems mediante el Dise&#241;ador | Microsoft Docs"
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
  - "elementos de menú, deshabilitar"
  - "menús, deshabilitar elementos"
  - "MenuStrip (control) [Windows Forms], deshabilitar elementos de menú en el diseñador"
  - "ToolStripMenuItems, deshabilitar en el diseñador"
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Deshabilitar ToolStripMenuItems mediante el Dise&#241;ador
Puede limitar o ampliar los comandos que introducen los usuarios habilitando y deshabilitando los elementos de menú en respuesta a las actividades del usuario.  Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>.  Puede manipular en tiempo de diseño esta propiedad en la ventana **Propiedades** o mediante programación estableciéndola en código.  Para obtener más información, vea [Cómo: Deshabilitar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para deshabilitar un menú en tiempo de diseño  
  
1.  Con el elemento de menú seleccionado en el formulario, establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> en `false`.  
  
    > [!TIP]
    >  Al deshabilitar el primer elemento de menú o elemento de menú de nivel superior, se deshabilitan todos los elementos incluidos en el menú.  De forma similar, si deshabilita un elemento de menú que tenga elementos de submenú, deshabilitará los elementos de submenú.  Si ninguno de los comandos de un menú dado está disponible para el usuario, se considera una buena práctica de programación ocultar y deshabilitar todo el menú, para presentar una interfaz de usuario limpia.  Es esencial ocultar y deshabilitar el menú, ya que si sólo se oculta no se impide el acceso a los comandos de menú por medio de las teclas de método abreviado.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> de un elemento de menú de nivel superior en `false` para ocultar todo el menú.  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Cómo: Ocultar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)