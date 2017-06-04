---
title: "C&#243;mo: Ocultar ToolStripMenuItems mediante el Dise&#241;ador | Microsoft Docs"
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
  - "elementos de menú, ocultar"
  - "MenuStrip (control) [Windows Forms], ocultar elementos de menú en el diseñador"
  - "ToolStripMenuItems, ocultar elementos de menú en el diseñador"
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Ocultar ToolStripMenuItems mediante el Dise&#241;ador
Ocultar elementos de menú es un modo de controlar la interfaz de usuario de la aplicación y restringir los comandos de usuario.  Con frecuencia, se quiere ocultar un menú completo cuando todos sus elementos no están disponibles.  Esto supone menos distracciones para el usuario.  Es más, a veces es necesario ocultar y deshabilitar el menú o elemento de menú, ya que si sólo se oculta, no impide al usuario el acceso a los comandos de menú por medio de teclas de método abreviado.   Para obtener más información sobre cómo deshabilitar elementos de menú, vea [Cómo: Deshabilitar ToolStripMenuItems mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para ocultar un menú de nivel superior y sus elementos de submenú  
  
1.  Seleccione el elemento de menú de nivel superior y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> en `false`.  
  
     Cuando oculta el elemento de menú de nivel superior, también se ocultan todos los elementos de menú dentro de ese menú.  Si hace clic en cualquier lugar distinto de <xref:System.Windows.Forms.MenuStrip> después de establecer la propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> en `false`, todo el elemento de menú de nivel superior y sus elementos de submenú desaparecen del formulario, mostrando por tanto el efecto en tiempo de ejecución de la acción.  Para mostrar el elemento de menú de nivel superior en tiempo de diseño, haga clic en <xref:System.Windows.Forms.MenuStrip> en la **Bandeja de componentes**, en el **Esquema del documento** o en la parte superior de la cuadrícula de la propiedad.  
  
> [!NOTE]
>  Raramente ocultará un menú completo salvo para los menús secundarios de la interfaz de múltiples documentos \(MDI\) en un escenario de combinación.  
  
### Para ocultar un elemento de submenú  
  
1.  Seleccione el elemento de submenú y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> en `false`.  
  
     Cuando oculta un elemento de submenú, permanece visible en el formulario en tiempo de diseño, de tal forma que puede seleccionarlo fácilmente para un trabajo posterior.  Se ocultará realmente en tiempo de ejecución.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [Cómo: Deshabilitar ToolStripMenuItems mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)