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
ms.openlocfilehash: e862f02e736cb8507dde5036700d751f8af0a226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552875"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="3b8ff-102">Información general sobre ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b8ff-102">ContextMenu Overview</span></span>
<span data-ttu-id="3b8ff-103">El <xref:System.Windows.Controls.ContextMenu> clase representa el elemento que expone la funcionalidad mediante el uso de un determinado contexto <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="3b8ff-104">Normalmente, un usuario expone el <xref:System.Windows.Controls.ContextMenu> en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] haciendo clic en el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="3b8ff-105">Este tema se presentan los <xref:System.Windows.Controls.ContextMenu> elemento y proporciona ejemplos de cómo se usa en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y el código.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="3b8ff-106">Control ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b8ff-106">ContextMenu Control</span></span>  
 <span data-ttu-id="3b8ff-107">Un <xref:System.Windows.Controls.ContextMenu> se adjunta a un control específico.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="3b8ff-108">El <xref:System.Windows.Controls.ContextMenu> elemento le permite presentar a los usuarios con una lista de elementos que especifican comandos u opciones que están asociados a un control determinado, por ejemplo, un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="3b8ff-109">Los usuarios hacen clic con el botón derecho en el control para que aparezca el menú.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="3b8ff-110">Normalmente, al hacer clic en un <xref:System.Windows.Controls.MenuItem> abre un submenú o hace que una aplicación para llevar a cabo un comando.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="3b8ff-111">Creación de elementos ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b8ff-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="3b8ff-112">Los ejemplos siguientes muestran cómo crear un <xref:System.Windows.Controls.ContextMenu> con submenús.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="3b8ff-113">El <xref:System.Windows.Controls.ContextMenu> controles están asociados a los controles de botón.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="3b8ff-114">Aplicación de estilos a un control ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b8ff-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="3b8ff-115">Mediante el uso de un control <xref:System.Windows.Style>, puede cambiar considerablemente la apariencia y el comportamiento de un <xref:System.Windows.Controls.ContextMenu> sin necesidad de escribir un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="3b8ff-116">Además de establecer propiedades visuales, también puede aplicar estilos a las partes de un control.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="3b8ff-117">Por ejemplo, puede cambiar el comportamiento de los elementos del control mediante propiedades, o puede agregar partes a, o cambiar el diseño de, un <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="3b8ff-118">Los ejemplos siguientes muestran varias maneras de agregar estilos para <xref:System.Windows.Controls.ContextMenu> controles.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="3b8ff-119">En el primer ejemplo se define un estilo denominado `SimpleSysResources`, que muestra cómo usar la configuración actual del sistema en el estilo.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="3b8ff-120">El ejemplo se asigna <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> como el <xref:System.Windows.Controls.Control.Background%2A> color y <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> como el <xref:System.Windows.Controls.Control.Foreground%2A> color de la <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="3b8ff-121">En el ejemplo siguiente se usa el <xref:System.Windows.Trigger> elemento que se va a cambiar la apariencia de un <xref:System.Windows.Controls.Menu> en respuesta a eventos que se producen en el <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="3b8ff-122">Cuando un usuario mueve el mouse sobre el menú, el aspecto de los <xref:System.Windows.Controls.ContextMenu> cambios de elementos.</span><span class="sxs-lookup"><span data-stu-id="3b8ff-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b8ff-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b8ff-123">See Also</span></span>  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [<span data-ttu-id="3b8ff-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="3b8ff-124">ContextMenu</span></span>](../../../../docs/framework/wpf/controls/contextmenu.md)  
 <span data-ttu-id="3b8ff-125">[ContextMenu Styles and Templates](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md) (Estilos y plantillas de ContextMenu)</span><span class="sxs-lookup"><span data-stu-id="3b8ff-125">[ContextMenu Styles and Templates](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)</span></span>  
 <span data-ttu-id="3b8ff-126">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053) (Ejemplo de galería de controles de WPF)</span><span class="sxs-lookup"><span data-stu-id="3b8ff-126">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)</span></span>
