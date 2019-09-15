---
title: PresentationOptions:Freeze (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991428"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="616e4-102">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="616e4-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="616e4-103">Establece el <xref:System.Windows.Freezable.IsFrozen%2A> `true` estado en en el elemento <xref:System.Windows.Freezable> contenedor.</span><span class="sxs-lookup"><span data-stu-id="616e4-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="616e4-104">El comportamiento predeterminado de <xref:System.Windows.Freezable> un sin `PresentationOptions:Freeze` el atributo especificado es <xref:System.Windows.Freezable.IsFrozen%2A> que `false` está en tiempo de carga y depende del <xref:System.Windows.Freezable> comportamiento general en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="616e4-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="616e4-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="616e4-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="616e4-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="616e4-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="616e4-107">Un prefijo de espacio de nombres XML, que puede ser cualquier cadena de prefijo válida, según la especificación de XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="616e4-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="616e4-108">El prefijo `PresentationOptions` se usa para fines de identificación en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="616e4-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="616e4-109">Un elemento que crea una instancia de cualquier clase <xref:System.Windows.Freezable>derivada de.</span><span class="sxs-lookup"><span data-stu-id="616e4-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="616e4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="616e4-110">Remarks</span></span>  
 <span data-ttu-id="616e4-111">El `Freeze` atributo es el único atributo u otro elemento de programación definido en `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` el espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="616e4-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="616e4-112">El `Freeze` atributo existe en este espacio de nombres especial específicamente para que se pueda designar como ignorable, mediante el [atributo MC: ignorable](mc-ignorable-attribute.md) como parte de las declaraciones del elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="616e4-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="616e4-113">La razón por `Freeze` la que se debe poder omitir es porque no todas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] las implementaciones del procesador pueden inmovilizar <xref:System.Windows.Freezable> en tiempo de carga; esta funcionalidad no forma parte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de la especificación.</span><span class="sxs-lookup"><span data-stu-id="616e4-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="616e4-114">La capacidad de procesar el `Freeze` atributo se integra específicamente en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador que procesa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] las aplicaciones compiladas.</span><span class="sxs-lookup"><span data-stu-id="616e4-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="616e4-115">El atributo no es compatible con ninguna clase y la sintaxis del atributo no es extensible ni modificable.</span><span class="sxs-lookup"><span data-stu-id="616e4-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="616e4-116">Si está implementando su propio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, puede elegir en paralelo el comportamiento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de congelación del procesador al procesar `Freeze` el atributo <xref:System.Windows.Freezable> en los elementos en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="616e4-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="616e4-117">Cualquier valor para el `Freeze` atributo distinto de `true` (no distingue entre mayúsculas y minúsculas) genera un error de tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="616e4-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="616e4-118">(Especificar el `Freeze` atributo como `false` no es un error, pero ya es el valor predeterminado, por lo que establecer `false` en no hace nada).</span><span class="sxs-lookup"><span data-stu-id="616e4-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="616e4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="616e4-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="616e4-120">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="616e4-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="616e4-121">mc:Ignorable (atributo)</span><span class="sxs-lookup"><span data-stu-id="616e4-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
