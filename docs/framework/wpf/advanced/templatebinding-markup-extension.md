---
title: "Extensión de marcado TemplateBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ab8645de78a79f4bd47fa436699af002db99b9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="8a672-102">Extensión de marcado TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="8a672-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="8a672-103">Vincula el valor de una propiedad de una plantilla de control para que sea el valor de otra propiedad del control con plantilla.</span><span class="sxs-lookup"><span data-stu-id="8a672-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="8a672-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="8a672-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="8a672-105">Uso de atributos XAML (para la propiedad Setter de una plantilla o estilo)</span><span class="sxs-lookup"><span data-stu-id="8a672-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="8a672-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="8a672-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="8a672-107">Propiedad <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> que se va establecer en la sintaxis del establecedor.</span><span class="sxs-lookup"><span data-stu-id="8a672-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="8a672-108">Otra propiedad de dependencia existente en el tipo con plantilla, especificada por el valor de <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8a672-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="8a672-109">o bien</span><span class="sxs-lookup"><span data-stu-id="8a672-109">- or -</span></span><br /><br /> <span data-ttu-id="8a672-110">Nombre de propiedad "relacionada" que se define por un tipo diferente del tipo de destino que se va a convertir en un tipo con plantilla.</span><span class="sxs-lookup"><span data-stu-id="8a672-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="8a672-111">En realidad, se trata de un objeto <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="8a672-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="8a672-112">Vea [sintaxis de PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="8a672-112">See [PropertyPath XAML Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a672-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a672-113">Remarks</span></span>  
 <span data-ttu-id="8a672-114">A `TemplateBinding` es una forma optimizada de un [enlace](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) para escenarios de plantilla, análogos a un `Binding` construidos con `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="8a672-114">A `TemplateBinding` is an optimized form of a [Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="8a672-115">`TemplateBinding` siempre es un enlace unidireccional, aunque las propiedades implicadas establezcan por defecto un enlace bidireccional.</span><span class="sxs-lookup"><span data-stu-id="8a672-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="8a672-116">Ambas propiedades implicadas deben ser propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="8a672-116">Both properties involved must be dependency properties.</span></span>  
  
 <span data-ttu-id="8a672-117">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) es otra extensión de marcado que a veces se usa en conjunción con o en lugar de `TemplateBinding` con el fin de realizar el enlace de la propiedad relativa dentro de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="8a672-117">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="8a672-118">Describir plantillas de control como un concepto no se trata aquí; Para obtener más información, consulte [plantillas y estilos de Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8a672-118">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="8a672-119">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="8a672-119">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="8a672-120">El token de cadena que se proporciona después de la cadena de identificador `TemplateBinding` se asigna como valor de <xref:System.Windows.TemplateBindingExtension.Property%2A> de la clase de extensión <xref:System.Windows.TemplateBindingExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="8a672-120">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="8a672-121">La sintaxis de elementos de objeto es posible, pero no se muestra porque no tiene ninguna aplicación en el mundo real.</span><span class="sxs-lookup"><span data-stu-id="8a672-121">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="8a672-122">`TemplateBinding` se emplea para rellenar los valores dentro de los establecedores, mediante expresiones evaluadas, y el uso de la sintaxis de elementos de objeto para que `TemplateBinding` rellene la sintaxis de elementos de propiedad de `<Setter.Property>` aplica un grado de detalle innecesario.</span><span class="sxs-lookup"><span data-stu-id="8a672-122">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="8a672-123">`TemplateBinding` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.TemplateBindingExtension.Property%2A> como un par de propiedad=valor:</span><span class="sxs-lookup"><span data-stu-id="8a672-123">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="8a672-124">El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.</span><span class="sxs-lookup"><span data-stu-id="8a672-124">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="8a672-125">Dado que `TemplateBinding` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.</span><span class="sxs-lookup"><span data-stu-id="8a672-125">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="8a672-126">En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación del procesador XAML, el control para esta extensión de marcado se define por la <xref:System.Windows.TemplateBindingExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="8a672-126">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="8a672-127">`TemplateBinding` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="8a672-127">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="8a672-128">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="8a672-128">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="8a672-129">Todas las extensiones de marcado de XAML utilizan la `{` y `}` caracteres en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe procesar el atributo.</span><span class="sxs-lookup"><span data-stu-id="8a672-129">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="8a672-130">Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="8a672-130">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a672-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a672-131">See Also</span></span>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="8a672-132">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="8a672-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="8a672-133">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="8a672-133">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="8a672-134">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="8a672-134">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="8a672-135">RelativeSource (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="8a672-135">RelativeSource MarkupExtension</span></span>](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [<span data-ttu-id="8a672-136">Binding (extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="8a672-136">Binding Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
