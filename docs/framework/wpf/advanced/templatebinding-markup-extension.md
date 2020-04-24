---
title: Extensión de marcado TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 8c631a5a78db90187f0375181d4d4d1832159b7d
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646170"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="62140-102">Extensión de marcado TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="62140-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="62140-103">Vincula el valor de una propiedad de una plantilla de control para que sea el valor de otra propiedad del control con plantilla.</span><span class="sxs-lookup"><span data-stu-id="62140-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="62140-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="62140-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="62140-105">Uso de atributos XAML (para la propiedad Setter de una plantilla o estilo)</span><span class="sxs-lookup"><span data-stu-id="62140-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="62140-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="62140-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="62140-107">Propiedad <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> que se va establecer en la sintaxis del establecedor.</span><span class="sxs-lookup"><span data-stu-id="62140-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="62140-108">Otra propiedad de dependencia existente en el tipo con plantilla, especificada por el valor de <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="62140-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="62140-109">O bien</span><span class="sxs-lookup"><span data-stu-id="62140-109">- or -</span></span><br /><br /> <span data-ttu-id="62140-110">Nombre de propiedad "relacionada" que se define por un tipo diferente del tipo de destino que se va a convertir en un tipo con plantilla.</span><span class="sxs-lookup"><span data-stu-id="62140-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="62140-111">En realidad, se trata de un objeto <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="62140-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="62140-112">Consulte [Sintaxis XAML PropertyPath](propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="62140-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62140-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62140-113">Remarks</span></span>  
 <span data-ttu-id="62140-114">A `TemplateBinding` es una forma optimizada de un [enlace](binding-markup-extension.md) para `Binding` escenarios `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`de plantilla, análogo a un construido con .</span><span class="sxs-lookup"><span data-stu-id="62140-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`.</span></span> <span data-ttu-id="62140-115">`TemplateBinding` siempre es un enlace unidireccional, aunque las propiedades implicadas establezcan por defecto un enlace bidireccional.</span><span class="sxs-lookup"><span data-stu-id="62140-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="62140-116">Ambas propiedades implicadas deben ser propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="62140-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="62140-117">Para lograr el enlace bidireccional a un elemento primario con `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`plantilla, utilice la siguiente instrucción de enlace en su lugar.</span><span class="sxs-lookup"><span data-stu-id="62140-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span>
  
 <span data-ttu-id="62140-118">[RelativeSource](relativesource-markupextension.md) es otra extensión de marcado que a `TemplateBinding` veces se usa junto con o en lugar de para realizar el enlace de propiedad relativa dentro de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="62140-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="62140-119">La descripción de plantillas de control como un concepto no se trata aquí; Para obtener más información, consulte [Estilos de control y plantillas](../controls/control-styles-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="62140-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="62140-120">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="62140-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="62140-121">El token de cadena que se proporciona después de la cadena de identificador `TemplateBinding` se asigna como valor de <xref:System.Windows.TemplateBindingExtension.Property%2A> de la clase de extensión <xref:System.Windows.TemplateBindingExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="62140-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="62140-122">La sintaxis de elementos de objeto es posible, pero no se muestra porque no tiene ninguna aplicación en el mundo real.</span><span class="sxs-lookup"><span data-stu-id="62140-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="62140-123">`TemplateBinding` se emplea para rellenar los valores dentro de los establecedores, mediante expresiones evaluadas, y el uso de la sintaxis de elementos de objeto para que `TemplateBinding` rellene la sintaxis de elementos de propiedad de `<Setter.Property>` aplica un grado de detalle innecesario.</span><span class="sxs-lookup"><span data-stu-id="62140-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="62140-124">`TemplateBinding` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.TemplateBindingExtension.Property%2A> como un par de propiedad=valor:</span><span class="sxs-lookup"><span data-stu-id="62140-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="62140-125">El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.</span><span class="sxs-lookup"><span data-stu-id="62140-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="62140-126">Dado que `TemplateBinding` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.</span><span class="sxs-lookup"><span data-stu-id="62140-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="62140-127">En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la implementación del procesador XAML, la <xref:System.Windows.TemplateBindingExtension> clase define el control de esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="62140-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="62140-128">`TemplateBinding` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="62140-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="62140-129">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="62140-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="62140-130">Todas las extensiones `{` de `}` marcado en XAML usan los caracteres y en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el atributo.</span><span class="sxs-lookup"><span data-stu-id="62140-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="62140-131">Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="62140-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62140-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62140-132">See also</span></span>

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="62140-133">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="62140-133">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="62140-134">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="62140-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="62140-135">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="62140-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="62140-136">Extensión de marcado RelativeSource</span><span class="sxs-lookup"><span data-stu-id="62140-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="62140-137">Enlazar extensión de marcado</span><span class="sxs-lookup"><span data-stu-id="62140-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
