---
title: PresentationOptions:Freeze (Atributo)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8f1a876f65941afb159d4c3d8904ab4426d9177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="88d4e-102">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="88d4e-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="88d4e-103">Establece el <xref:System.Windows.Freezable.IsFrozen%2A> estado `true` en la que contiene <xref:System.Windows.Freezable> elemento.</span><span class="sxs-lookup"><span data-stu-id="88d4e-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="88d4e-104">Comportamiento para predeterminado un <xref:System.Windows.Freezable> sin el `PresentationOptions:Freeze` el atributo especificado es que <xref:System.Windows.Freezable.IsFrozen%2A> es `false` en tiempo de carga y depende de general <xref:System.Windows.Freezable> comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="88d4e-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="88d4e-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="88d4e-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="88d4e-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="88d4e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="88d4e-107">Un prefijo de espacio de nombres XML, que puede ser cualquier cadena de prefijo, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="88d4e-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="88d4e-108">El prefijo `PresentationOptions` se utiliza para propósitos de identificación en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="88d4e-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="88d4e-109">Un elemento que se crea una instancia de cualquier clase derivada de <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="88d4e-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88d4e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88d4e-110">Remarks</span></span>  
 <span data-ttu-id="88d4e-111">El `Freeze` es el único atributo u otro elemento de programación definido en el `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="88d4e-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="88d4e-112">El `Freeze` atributo existe en este espacio de nombres especial específicamente para que pueden designarse como puede pasar por alto, con [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) como parte de las declaraciones de elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="88d4e-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="88d4e-113">El motivo que `Freeze` debe ser capaz de ser puede pasar por alto es porque no todos los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] las implementaciones de procesador pueden inmovilizar un <xref:System.Windows.Freezable> en tiempo de carga; esta funcionalidad no está forma parte de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] especificación.</span><span class="sxs-lookup"><span data-stu-id="88d4e-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="88d4e-114">La capacidad para procesar el `Freeze` atributo específicamente integrado en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador que procesa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para aplicaciones compiladas.</span><span class="sxs-lookup"><span data-stu-id="88d4e-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="88d4e-115">El atributo no es compatible con cualquier clase, y la sintaxis de atributo no es extensible ni modificable.</span><span class="sxs-lookup"><span data-stu-id="88d4e-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="88d4e-116">Si está implementando su propio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador puede hacer que el comportamiento de inmovilización de en paralelo el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador al procesar la `Freeze` atributo <xref:System.Windows.Freezable> elementos en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="88d4e-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="88d4e-117">Cualquier valor para el `Freeze` atributo distinto de `true` (no entre mayúsculas y minúsculas) genera un error en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="88d4e-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="88d4e-118">(Especificar el `Freeze` atributo como `false` no es un error, pero que ya es el valor predeterminado, por lo que si se establece en `false` no hace nada).</span><span class="sxs-lookup"><span data-stu-id="88d4e-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d4e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="88d4e-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="88d4e-120">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="88d4e-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="88d4e-121">mc:Ignorable (atributo)</span><span class="sxs-lookup"><span data-stu-id="88d4e-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
