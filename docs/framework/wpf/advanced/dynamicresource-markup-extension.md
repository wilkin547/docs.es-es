---
title: "Extensión de marcado DynamicResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f6c8500f9b9cd6d617789a2da3444519971ae81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="aea7f-102">Extensión de marcado DynamicResource</span><span class="sxs-lookup"><span data-stu-id="aea7f-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="aea7f-103">Proporciona un valor para cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo de propiedad aplazando ese valor para que sea una referencia a un recurso definido.</span><span class="sxs-lookup"><span data-stu-id="aea7f-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="aea7f-104">Comportamiento de búsqueda de ese recurso es análogo a la búsqueda de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aea7f-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="aea7f-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="aea7f-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="aea7f-106">Uso de elementos de propiedad XAML</span><span class="sxs-lookup"><span data-stu-id="aea7f-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="aea7f-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="aea7f-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="aea7f-108">Clave del recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="aea7f-108">The key for the requested resource.</span></span> <span data-ttu-id="aea7f-109">Esta clave se asignó inicialmente por el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) si un recurso se creó en el marcado, o se proporcionó como el `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.</span><span class="sxs-lookup"><span data-stu-id="aea7f-109">This key was initially assigned by the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aea7f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aea7f-110">Remarks</span></span>  
 <span data-ttu-id="aea7f-111">Un `DynamicResource` creará una expresión temporal durante la compilación inicial y, por tanto, aplazar la consulta de recursos hasta que el valor de recurso solicitado se necesite realmente para construir un objeto.</span><span class="sxs-lookup"><span data-stu-id="aea7f-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="aea7f-112">Esto puede ser después de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se carga la página.</span><span class="sxs-lookup"><span data-stu-id="aea7f-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="aea7f-113">El valor del recurso se encontrará en función de búsqueda de la clave en todos los diccionarios de recursos activos a partir del ámbito de la página actual y se sustituye por la expresión de marcador de posición de la compilación.</span><span class="sxs-lookup"><span data-stu-id="aea7f-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aea7f-114">En términos de prioridad de la propiedad de dependencia, una `DynamicResource` expresión es equivalente a la posición donde se aplica la referencia de recurso dinámico.</span><span class="sxs-lookup"><span data-stu-id="aea7f-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="aea7f-115">Si establece un valor local para una propiedad que previamente tenía un `DynamicResource` expresión como el valor local, el `DynamicResource` se ha quitado completamente.</span><span class="sxs-lookup"><span data-stu-id="aea7f-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="aea7f-116">Para obtener más información, consulte [Prioridad de los valores de propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-116">For details, see [Dependency Property Value Precedence](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="aea7f-117">Son especialmente adecuadas para determinados escenarios de acceso de recurso `DynamicResource` en contraposición a un [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span></span> <span data-ttu-id="aea7f-118">Vea [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) para obtener información sobre las ventajas relativas y las implicaciones de rendimiento de `DynamicResource` y `StaticResource`.</span><span class="sxs-lookup"><span data-stu-id="aea7f-118">See [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="aea7f-119">Especificado <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente determinado por [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) en algún nivel en la página, aplicación, los temas de control disponibles y recursos externos o recursos del sistema y la búsqueda de recursos se realizará en ese orden.</span><span class="sxs-lookup"><span data-stu-id="aea7f-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="aea7f-120">Para obtener más información acerca de las búsquedas de recursos para los recursos estáticos y dinámicos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="aea7f-121">Una clave de recurso puede ser cualquier cadena definida en el [XamlName (gramática)](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-121">A resource key may be any string defined in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="aea7f-122">Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="aea7f-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="aea7f-123">Un <xref:System.Type> clave es fundamental para cómo pueden aplicarse estilos a controles por los temas.</span><span class="sxs-lookup"><span data-stu-id="aea7f-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="aea7f-124">Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-124">For more information, see [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]<span data-ttu-id="aea7f-125">para la búsqueda de valores de recursos, como <xref:System.Windows.FrameworkElement.FindResource%2A>, siga la misma lógica de búsqueda de recursos que usa `DynamicResource`.</span><span class="sxs-lookup"><span data-stu-id="aea7f-125"> for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="aea7f-126">Es la manera declarativa alternativa de hacer referencia a un recurso como una [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="aea7f-127">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="aea7f-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="aea7f-128">El token de cadena que se proporciona después de la cadena de identificador `DynamicResource` se asigna como valor de <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.DynamicResourceExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="aea7f-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="aea7f-129">`DynamicResource`puede usarse en la sintaxis de elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="aea7f-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="aea7f-130">En este caso, especificando el valor de la <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> propiedad es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="aea7f-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="aea7f-131">`DynamicResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> como un par de propiedad=valor:</span><span class="sxs-lookup"><span data-stu-id="aea7f-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="aea7f-132">El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.</span><span class="sxs-lookup"><span data-stu-id="aea7f-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="aea7f-133">Dado que `DynamicResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.</span><span class="sxs-lookup"><span data-stu-id="aea7f-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="aea7f-134">En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador, el control para esta extensión de marcado se define por la <xref:System.Windows.DynamicResourceExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="aea7f-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="aea7f-135">`DynamicResource` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="aea7f-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="aea7f-136">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="aea7f-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="aea7f-137">Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="aea7f-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="aea7f-138">Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="aea7f-138">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea7f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="aea7f-139">See Also</span></span>  
 [<span data-ttu-id="aea7f-140">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="aea7f-140">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="aea7f-141">Recursos y código</span><span class="sxs-lookup"><span data-stu-id="aea7f-141">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="aea7f-142">x:Key (Directiva)</span><span class="sxs-lookup"><span data-stu-id="aea7f-142">x:Key Directive</span></span>](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [<span data-ttu-id="aea7f-143">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="aea7f-143">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="aea7f-144">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="aea7f-144">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="aea7f-145">StaticResource (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="aea7f-145">StaticResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [<span data-ttu-id="aea7f-146">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="aea7f-146">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
