---
title: "Informaci&#243;n general sobre ContextMenu | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ContextMenu (controles) [WPF], acerca de ContextMenu (controles)"
  - "controles, ContextMenu"
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre ContextMenu
La clase <xref:System.Windows.Controls.ContextMenu> representa el elemento que expone la funcionalidad mediante un control <xref:System.Windows.Controls.Menu> específico del contexto.  Normalmente, el usuario expone el control <xref:System.Windows.Controls.ContextMenu> en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] haciendo clic con el botón secundario del mouse.  En este tema se presenta el elemento <xref:System.Windows.Controls.ContextMenu> y se incluyen ejemplos de cómo utilizarlo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en código.  
  
   
  
<a name="contextmenu_control"></a>   
## Control ContextMenu  
 El control <xref:System.Windows.Controls.ContextMenu> está asociado a un control concreto.  El elemento <xref:System.Windows.Controls.ContextMenu> permite presentar a los usuarios una lista de elementos que especifican opciones o comandos que están asociados a un control determinado, por ejemplo, un control <xref:System.Windows.Controls.Button>.  Los usuarios hacen clic en el control con el botón secundario del mouse para que aparezca el menú.  Normalmente, al hacer clic en un elemento <xref:System.Windows.Controls.MenuItem>, se abre un submenú o una aplicación a fin de ejecutar un comando.  
  
<a name="creating_contextmenus"></a>   
## Crear controles ContextMenu  
 En los ejemplos siguientes, se muestra cómo crear un control <xref:System.Windows.Controls.ContextMenu> con submenús.  Los controles <xref:System.Windows.Controls.ContextMenu> están asociados a controles de botón.  
  
 [!code-xml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## Aplicar estilos a un control ContextMenu  
 Mediante la clase <xref:System.Windows.Style>, puede cambiar radicalmente la apariencia y el comportamiento de un control <xref:System.Windows.Controls.ContextMenu> sin tener que escribir un control personalizado.  Además de establecer propiedades visuales, también puede aplicar estilos a las distintas partes de un control.  Por ejemplo, puede cambiar el comportamiento de las distintas partes del control mediante propiedades, o bien, puede agregar o cambiar el diseño de las distintas partes de un control <xref:System.Windows.Controls.ContextMenu>.  En los ejemplos siguientes, se muestran varias maneras de agregar estilos a controles <xref:System.Windows.Controls.ContextMenu>.  
  
 En el primer ejemplo se define un estilo denominado `SimpleSysResources`, que muestra cómo utilizar la configuración actual del sistema en el estilo.  En el ejemplo se asigna <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> como color de <xref:System.Windows.Controls.Control.Background%2A> y <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> como color de <xref:System.Windows.Controls.Control.Foreground%2A> del control <xref:System.Windows.Controls.ContextMenu>.  
  
```  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 En el ejemplo siguiente se utiliza el elemento <xref:System.Windows.Trigger> para cambiar la apariencia de un control <xref:System.Windows.Controls.Menu> en respuesta a los eventos que se provocan en el control <xref:System.Windows.Controls.ContextMenu>.  Cuando el usuario mueve el mouse sobre el menú, cambia la apariencia de los elementos de <xref:System.Windows.Controls.ContextMenu>.  
  
```  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## Vea también  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.Menu>   
 <xref:System.Windows.Controls.MenuItem>   
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)   
 [Estilos y plantillas de ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)   
 [Ejemplo WPF Controls Gallery](http://go.microsoft.com/fwlink/?LinkID=160053)