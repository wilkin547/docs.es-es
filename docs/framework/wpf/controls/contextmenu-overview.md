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
# <a name="contextmenu-overview"></a><span data-ttu-id="c8737-102">Información general sobre ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c8737-102">ContextMenu Overview</span></span>
<span data-ttu-id="c8737-103">La <xref:System.Windows.Controls.ContextMenu> clase representa el elemento que expone la funcionalidad <xref:System.Windows.Controls.Menu>mediante un archivo .</span><span class="sxs-lookup"><span data-stu-id="c8737-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="c8737-104">Normalmente, un usuario <xref:System.Windows.Controls.ContextMenu> expone [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] el en el haciendo clic con el botón derecho del ratón.</span><span class="sxs-lookup"><span data-stu-id="c8737-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="c8737-105">En este tema <xref:System.Windows.Controls.ContextMenu> se presenta el elemento y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se proporcionan ejemplos de cómo usarlo y código.</span><span class="sxs-lookup"><span data-stu-id="c8737-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="c8737-106">Control ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c8737-106">ContextMenu Control</span></span>  
 <span data-ttu-id="c8737-107">A <xref:System.Windows.Controls.ContextMenu> se adjunta a un control específico.</span><span class="sxs-lookup"><span data-stu-id="c8737-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="c8737-108">El <xref:System.Windows.Controls.ContextMenu> elemento permite presentar a los usuarios una lista de elementos que especifican comandos u opciones que están asociados a un control determinado, por ejemplo, un <xref:System.Windows.Controls.Button>archivo .</span><span class="sxs-lookup"><span data-stu-id="c8737-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="c8737-109">Los usuarios hacen clic con el botón derecho en el control para que aparezca el menú.</span><span class="sxs-lookup"><span data-stu-id="c8737-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="c8737-110">Normalmente, al <xref:System.Windows.Controls.MenuItem> hacer clic en un se abre un submenú o hace que una aplicación lleve a cabo un comando.</span><span class="sxs-lookup"><span data-stu-id="c8737-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="c8737-111">Creación de elementos ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c8737-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="c8737-112">En los ejemplos siguientes <xref:System.Windows.Controls.ContextMenu> se muestra cómo crear un con submenús.</span><span class="sxs-lookup"><span data-stu-id="c8737-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="c8737-113">Los <xref:System.Windows.Controls.ContextMenu> controles están conectados a los controles de botón.</span><span class="sxs-lookup"><span data-stu-id="c8737-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="c8737-114">Aplicación de estilos a un control ContextMenu</span><span class="sxs-lookup"><span data-stu-id="c8737-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="c8737-115">Mediante el <xref:System.Windows.Style>uso de un control , puede <xref:System.Windows.Controls.ContextMenu> cambiar drásticamente la apariencia y el comportamiento de un sin escribir un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="c8737-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="c8737-116">Además de establecer propiedades visuales, también puede aplicar estilos a las partes de un control.</span><span class="sxs-lookup"><span data-stu-id="c8737-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="c8737-117">Por ejemplo, puede cambiar el comportamiento de partes del control mediante propiedades, o puede agregar <xref:System.Windows.Controls.ContextMenu>partes a un archivo .</span><span class="sxs-lookup"><span data-stu-id="c8737-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="c8737-118">En los ejemplos siguientes se <xref:System.Windows.Controls.ContextMenu> muestran varias formas de agregar estilos a los controles.</span><span class="sxs-lookup"><span data-stu-id="c8737-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="c8737-119">En el primer ejemplo se define un estilo denominado `SimpleSysResources`, que muestra cómo usar la configuración actual del sistema en el estilo.</span><span class="sxs-lookup"><span data-stu-id="c8737-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="c8737-120">El ejemplo <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> se <xref:System.Windows.Controls.Control.Background%2A> asigna <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> como <xref:System.Windows.Controls.Control.Foreground%2A> el color <xref:System.Windows.Controls.ContextMenu>y como el color del archivo .</span><span class="sxs-lookup"><span data-stu-id="c8737-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="c8737-121">En el ejemplo <xref:System.Windows.Trigger> siguiente se utiliza <xref:System.Windows.Controls.Menu> el elemento para cambiar la <xref:System.Windows.Controls.ContextMenu>apariencia de a en respuesta a los eventos que se generan en el archivo .</span><span class="sxs-lookup"><span data-stu-id="c8737-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="c8737-122">Cuando un usuario mueve el ratón sobre <xref:System.Windows.Controls.ContextMenu> el menú, cambia la apariencia de los elementos.</span><span class="sxs-lookup"><span data-stu-id="c8737-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8737-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8737-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="c8737-124">Contextmenu</span><span class="sxs-lookup"><span data-stu-id="c8737-124">ContextMenu</span></span>](contextmenu.md)
- <span data-ttu-id="c8737-125">[ContextMenu Styles and Templates](contextmenu-styles-and-templates.md) (Estilos y plantillas de ContextMenu)</span><span class="sxs-lookup"><span data-stu-id="c8737-125">[ContextMenu Styles and Templates](contextmenu-styles-and-templates.md)</span></span>
- <span data-ttu-id="c8737-126">[WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)</span><span class="sxs-lookup"><span data-stu-id="c8737-126">[WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)</span></span>
