---
title: "Extensión de marcado ComponentResourceKey"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f959318c5991fea2df92ff8000e85345fb35ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="340e1-102">Extensión de marcado ComponentResourceKey</span><span class="sxs-lookup"><span data-stu-id="340e1-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="340e1-103">Define y hace referencia a las claves de recursos que se cargan desde ensamblados externos.</span><span class="sxs-lookup"><span data-stu-id="340e1-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="340e1-104">Esto permite una búsqueda de recursos especificar un tipo de destino en un ensamblado, en lugar de un diccionario de recursos explícito en un ensamblado o en una clase.</span><span class="sxs-lookup"><span data-stu-id="340e1-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="340e1-105">Uso de atributos XAML (clave de configuración, compact)</span><span class="sxs-lookup"><span data-stu-id="340e1-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="340e1-106">Uso de atributos XAML (clave de valor, detallado)</span><span class="sxs-lookup"><span data-stu-id="340e1-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="340e1-107">Uso de atributos XAML (recurso de solicitud, compact)</span><span class="sxs-lookup"><span data-stu-id="340e1-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="340e1-108">Uso de atributos XAML (recurso de solicitud, detallado)</span><span class="sxs-lookup"><span data-stu-id="340e1-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="340e1-109">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="340e1-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="340e1-110">El nombre del público [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] tipo que se define en el ensamblado de recursos.</span><span class="sxs-lookup"><span data-stu-id="340e1-110">The name of the public [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="340e1-111">La clave para el recurso.</span><span class="sxs-lookup"><span data-stu-id="340e1-111">The key for the resource.</span></span> <span data-ttu-id="340e1-112">Cuando se buscan recursos, `targetID` será similar a la [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) del recurso.</span><span class="sxs-lookup"><span data-stu-id="340e1-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="340e1-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="340e1-113">Remarks</span></span>  
 <span data-ttu-id="340e1-114">Tal como se muestra en los usos de la anteriores, un {`ComponentResourceKey`} uso de la extensión de marcado se encuentra en dos lugares:</span><span class="sxs-lookup"><span data-stu-id="340e1-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
-   <span data-ttu-id="340e1-115">La definición de una tecla dentro de un diccionario de recursos de tema, proporcionados por el autor de un control.</span><span class="sxs-lookup"><span data-stu-id="340e1-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
-   <span data-ttu-id="340e1-116">Cuando se obtiene acceso a un recurso de temas desde el ensamblado, el control vuelve a crear plantillas pero desea utilizar los valores de propiedad que proceden de los recursos proporcionados por los temas del control.</span><span class="sxs-lookup"><span data-stu-id="340e1-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="340e1-117">Para hacer referencia a los recursos de componente que proceden de los temas, se recomienda generalmente utilizar `{DynamicResource}` en lugar de `{StaticResource}`.</span><span class="sxs-lookup"><span data-stu-id="340e1-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="340e1-118">Esto se muestra en los usos.</span><span class="sxs-lookup"><span data-stu-id="340e1-118">This is shown in the usages.</span></span> <span data-ttu-id="340e1-119">`{DynamicResource}`se recomienda porque el usuario puede cambiar el propio tema.</span><span class="sxs-lookup"><span data-stu-id="340e1-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="340e1-120">Si desea que el recurso de componente que mejor se ajuste la intención del autor de control para admitir un tema, debe habilitar la referencia de recurso de componente al que también sea dinámica.</span><span class="sxs-lookup"><span data-stu-id="340e1-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="340e1-121">El <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifica un tipo que existe en el ensamblado de destino donde se define realmente el recurso.</span><span class="sxs-lookup"><span data-stu-id="340e1-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="340e1-122">A `ComponentResourceKey` se puede definir y utilizar independientemente de saber exactamente donde la <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> está definido, pero finalmente debe resolver el tipo en los ensamblados que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="340e1-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="340e1-123">Un uso común para <xref:System.Windows.ComponentResourceKey> consiste en definir claves que, a continuación, se exponen como miembros de una clase.</span><span class="sxs-lookup"><span data-stu-id="340e1-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="340e1-124">Para este uso, utilice el <xref:System.Windows.ComponentResourceKey> constructor de clase, no la extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="340e1-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="340e1-125">Para obtener más información, consulte <xref:System.Windows.ComponentResourceKey>, o en la sección "Definir y hacer referencia a claves para recursos de tema" del tema [información general de creación de Control](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="340e1-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="340e1-126">Para establecer las claves tanto que hacen referencia a recursos con clave, la sintaxis de atributo se utiliza normalmente para el `ComponentResourceKey` extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="340e1-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="340e1-127">La sintaxis compacta se muestra se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> firma del constructor y el uso de parámetro posicional de una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="340e1-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="340e1-128">El orden en que el `targetTypeName` y `targetID` tienen es importante.</span><span class="sxs-lookup"><span data-stu-id="340e1-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="340e1-129">La sintaxis detallada se basa en el <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor predeterminado y, a continuación, Establece la <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> de forma que es análoga a una verdadera sintaxis de atributo en un elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="340e1-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> default constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="340e1-130">En la sintaxis detallada, no es importante el orden en el que se establecen las propiedades.</span><span class="sxs-lookup"><span data-stu-id="340e1-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="340e1-131">La relación y los mecanismos de estas dos alternativas (compacta y detallados) se describe con más detalle en el tema [las extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="340e1-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="340e1-132">Técnicamente, el valor de `targetID` puede ser cualquier objeto, no tiene que ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="340e1-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="340e1-133">Sin embargo, el uso más común en WPF es alinear el `targetID` valor con formularios que son cadenas y donde tales cadenas son válidas en el [XamlName (gramática)](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="340e1-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="340e1-134">`ComponentResourceKey`puede usarse en la sintaxis de elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="340e1-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="340e1-135">En este caso, especificar el valor de la <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> y <xref:System.Windows.ComponentResourceKey.ResourceId%2A> propiedades debe inicializar correctamente la extensión.</span><span class="sxs-lookup"><span data-stu-id="340e1-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="340e1-136">En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del lector, el control para esta extensión de marcado se define por la <xref:System.Windows.ComponentResourceKey> clase.</span><span class="sxs-lookup"><span data-stu-id="340e1-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="340e1-137">`ComponentResourceKey` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="340e1-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="340e1-138">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="340e1-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="340e1-139">Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="340e1-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="340e1-140">Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="340e1-140">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340e1-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="340e1-141">See Also</span></span>  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="340e1-142">Información general sobre la creación de controles</span><span class="sxs-lookup"><span data-stu-id="340e1-142">Control Authoring Overview</span></span>](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [<span data-ttu-id="340e1-143">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="340e1-143">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="340e1-144">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="340e1-144">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
