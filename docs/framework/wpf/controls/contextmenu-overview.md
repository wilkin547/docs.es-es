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
# <a name="contextmenu-overview"></a><span data-ttu-id="1b941-102">Información general sobre ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1b941-102">ContextMenu Overview</span></span>
<span data-ttu-id="1b941-103">La clase <xref:System.Windows.Controls.ContextMenu> representa el elemento que expone la funcionalidad mediante un <xref:System.Windows.Controls.Menu>específico del contexto.</span><span class="sxs-lookup"><span data-stu-id="1b941-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="1b941-104">Normalmente, un usuario expone el <xref:System.Windows.Controls.ContextMenu> en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] haciendo clic con el botón secundario del mouse.</span><span class="sxs-lookup"><span data-stu-id="1b941-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="1b941-105">En este tema se presenta el elemento <xref:System.Windows.Controls.ContextMenu> y se proporcionan ejemplos de cómo utilizarlo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código.</span><span class="sxs-lookup"><span data-stu-id="1b941-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="1b941-106">Control ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1b941-106">ContextMenu Control</span></span>  
 <span data-ttu-id="1b941-107">Un <xref:System.Windows.Controls.ContextMenu> se adjunta a un control específico.</span><span class="sxs-lookup"><span data-stu-id="1b941-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="1b941-108">El elemento <xref:System.Windows.Controls.ContextMenu> permite presentar a los usuarios una lista de elementos que especifican comandos u opciones que están asociados a un control determinado, por ejemplo, un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="1b941-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="1b941-109">Los usuarios hacen clic con el botón derecho en el control para que aparezca el menú.</span><span class="sxs-lookup"><span data-stu-id="1b941-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="1b941-110">Normalmente, al hacer clic en un <xref:System.Windows.Controls.MenuItem> se abre un submenú o se hace que una aplicación lleve a cabo un comando.</span><span class="sxs-lookup"><span data-stu-id="1b941-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="1b941-111">Creación de elementos ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1b941-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="1b941-112">En los siguientes ejemplos se muestra cómo crear un <xref:System.Windows.Controls.ContextMenu> con submenús.</span><span class="sxs-lookup"><span data-stu-id="1b941-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="1b941-113">Los controles de <xref:System.Windows.Controls.ContextMenu> se asocian a los controles de botón.</span><span class="sxs-lookup"><span data-stu-id="1b941-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="1b941-114">Aplicación de estilos a un control ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1b941-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="1b941-115">Mediante el uso de un <xref:System.Windows.Style>de control, puede cambiar drásticamente la apariencia y el comportamiento de un <xref:System.Windows.Controls.ContextMenu> sin necesidad de escribir un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="1b941-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="1b941-116">Además de establecer propiedades visuales, también puede aplicar estilos a las partes de un control.</span><span class="sxs-lookup"><span data-stu-id="1b941-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="1b941-117">Por ejemplo, puede cambiar el comportamiento de las partes del control mediante el uso de propiedades, o puede agregar elementos o cambiar el diseño de un <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="1b941-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="1b941-118">En los ejemplos siguientes se muestran varias maneras de agregar estilos a los controles <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="1b941-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="1b941-119">En el primer ejemplo se define un estilo denominado `SimpleSysResources`, que muestra cómo usar la configuración actual del sistema en el estilo.</span><span class="sxs-lookup"><span data-stu-id="1b941-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="1b941-120">En el ejemplo se asigna <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> como <xref:System.Windows.Controls.Control.Background%2A> color y <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> como color <xref:System.Windows.Controls.Control.Foreground%2A> del <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="1b941-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="1b941-121">En el ejemplo siguiente se usa el elemento <xref:System.Windows.Trigger> para cambiar la apariencia de un <xref:System.Windows.Controls.Menu> en respuesta a los eventos que se producen en el <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="1b941-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="1b941-122">Cuando un usuario mueve el mouse sobre el menú, cambia el aspecto de los elementos de <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="1b941-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b941-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b941-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="1b941-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1b941-124">ContextMenu</span></span>](contextmenu.md)
- <span data-ttu-id="1b941-125">[ContextMenu Styles and Templates](contextmenu-styles-and-templates.md) (Estilos y plantillas de ContextMenu)</span><span class="sxs-lookup"><span data-stu-id="1b941-125">[ContextMenu Styles and Templates](contextmenu-styles-and-templates.md)</span></span>
- <span data-ttu-id="1b941-126">[WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)</span><span class="sxs-lookup"><span data-stu-id="1b941-126">[WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)</span></span>
