---
title: Información general sobre ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: b973d47711632f4c0fe56f042545598272c79d2d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124369"
---
# <a name="contextmenu-overview"></a>Información general sobre ContextMenu
La clase <xref:System.Windows.Controls.ContextMenu> representa el elemento que expone la funcionalidad mediante un <xref:System.Windows.Controls.Menu>específico del contexto. Normalmente, un usuario expone el <xref:System.Windows.Controls.ContextMenu> en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] haciendo clic con el botón secundario del mouse. En este tema se presenta el elemento <xref:System.Windows.Controls.ContextMenu> y se proporcionan ejemplos de cómo utilizarlo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código.  

<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>Control ContextMenu  
 Un <xref:System.Windows.Controls.ContextMenu> se adjunta a un control específico. El elemento <xref:System.Windows.Controls.ContextMenu> permite presentar a los usuarios una lista de elementos que especifican comandos u opciones que están asociados a un control determinado, por ejemplo, un <xref:System.Windows.Controls.Button>. Los usuarios hacen clic con el botón derecho en el control para que aparezca el menú. Normalmente, al hacer clic en un <xref:System.Windows.Controls.MenuItem> se abre un submenú o se hace que una aplicación lleve a cabo un comando.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Creación de elementos ContextMenu  
 En los siguientes ejemplos se muestra cómo crear un <xref:System.Windows.Controls.ContextMenu> con submenús. Los controles de <xref:System.Windows.Controls.ContextMenu> se asocian a los controles de botón.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Aplicación de estilos a un control ContextMenu  
 Mediante el uso de un <xref:System.Windows.Style>de control, puede cambiar drásticamente la apariencia y el comportamiento de un <xref:System.Windows.Controls.ContextMenu> sin necesidad de escribir un control personalizado. Además de establecer propiedades visuales, también puede aplicar estilos a las partes de un control. Por ejemplo, puede cambiar el comportamiento de las partes del control mediante el uso de propiedades, o puede agregar elementos o cambiar el diseño de un <xref:System.Windows.Controls.ContextMenu>. En los ejemplos siguientes se muestran varias maneras de agregar estilos a los controles <xref:System.Windows.Controls.ContextMenu>.  
  
 En el primer ejemplo se define un estilo denominado `SimpleSysResources`, que muestra cómo usar la configuración actual del sistema en el estilo. En el ejemplo se asigna <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> como <xref:System.Windows.Controls.Control.Background%2A> color y <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> como color <xref:System.Windows.Controls.Control.Foreground%2A> del <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 En el ejemplo siguiente se usa el elemento <xref:System.Windows.Trigger> para cambiar la apariencia de un <xref:System.Windows.Controls.Menu> en respuesta a los eventos que se producen en el <xref:System.Windows.Controls.ContextMenu>. Cuando un usuario mueve el mouse sobre el menú, cambia el aspecto de los elementos de <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [ContextMenu](contextmenu.md)
- [ContextMenu Styles and Templates](contextmenu-styles-and-templates.md) (Estilos y plantillas de ContextMenu)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
