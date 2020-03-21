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
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185910"
---
# <a name="contextmenu-overview"></a>Información general sobre ContextMenu
La <xref:System.Windows.Controls.ContextMenu> clase representa el elemento que expone la funcionalidad <xref:System.Windows.Controls.Menu>mediante un archivo . Normalmente, un usuario <xref:System.Windows.Controls.ContextMenu> expone [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] el en el haciendo clic con el botón derecho del ratón. En este tema <xref:System.Windows.Controls.ContextMenu> se presenta el elemento y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se proporcionan ejemplos de cómo usarlo y código.  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>Control ContextMenu  
 A <xref:System.Windows.Controls.ContextMenu> se adjunta a un control específico. El <xref:System.Windows.Controls.ContextMenu> elemento permite presentar a los usuarios una lista de elementos que especifican comandos u opciones que están asociados a un control determinado, por ejemplo, un <xref:System.Windows.Controls.Button>archivo . Los usuarios hacen clic con el botón derecho en el control para que aparezca el menú. Normalmente, al <xref:System.Windows.Controls.MenuItem> hacer clic en un se abre un submenú o hace que una aplicación lleve a cabo un comando.  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>Creación de elementos ContextMenu  
 En los ejemplos siguientes <xref:System.Windows.Controls.ContextMenu> se muestra cómo crear un con submenús. Los <xref:System.Windows.Controls.ContextMenu> controles están conectados a los controles de botón.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>Aplicación de estilos a un control ContextMenu  
 Mediante el <xref:System.Windows.Style>uso de un control , puede <xref:System.Windows.Controls.ContextMenu> cambiar drásticamente la apariencia y el comportamiento de un sin escribir un control personalizado. Además de establecer propiedades visuales, también puede aplicar estilos a las partes de un control. Por ejemplo, puede cambiar el comportamiento de partes del control mediante propiedades, o puede agregar <xref:System.Windows.Controls.ContextMenu>partes a un archivo . En los ejemplos siguientes se <xref:System.Windows.Controls.ContextMenu> muestran varias formas de agregar estilos a los controles.  
  
 En el primer ejemplo se define un estilo denominado `SimpleSysResources`, que muestra cómo usar la configuración actual del sistema en el estilo. El ejemplo <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> se <xref:System.Windows.Controls.Control.Background%2A> asigna <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> como <xref:System.Windows.Controls.Control.Foreground%2A> el color <xref:System.Windows.Controls.ContextMenu>y como el color del archivo .  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 En el ejemplo <xref:System.Windows.Trigger> siguiente se utiliza <xref:System.Windows.Controls.Menu> el elemento para cambiar la <xref:System.Windows.Controls.ContextMenu>apariencia de a en respuesta a los eventos que se generan en el archivo . Cuando un usuario mueve el ratón sobre <xref:System.Windows.Controls.ContextMenu> el menú, cambia la apariencia de los elementos.  
  
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
- [Contextmenu](contextmenu.md)
- [ContextMenu Styles and Templates](contextmenu-styles-and-templates.md) (Estilos y plantillas de ContextMenu)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
