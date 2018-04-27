---
title: x:Type (Extensión de marcado)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db56c2bcdca14b87de320dfe19a6c364c76ecef7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="d2bff-102">x:Type (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="d2bff-102">x:Type Markup Extension</span></span>
<span data-ttu-id="d2bff-103">Proporciona el CLR <xref:System.Type> objeto que es el tipo subyacente para un tipo XAML especificado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d2bff-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="d2bff-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="d2bff-105">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="d2bff-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d2bff-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="d2bff-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="d2bff-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d2bff-107">Optional.</span></span> <span data-ttu-id="d2bff-108">Prefijo que se asigna un espacio de nombres XAML no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="d2bff-109">Especificar un prefijo con frecuencia no es necesario.</span><span class="sxs-lookup"><span data-stu-id="d2bff-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="d2bff-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="d2bff-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="d2bff-111">Requerido.</span><span class="sxs-lookup"><span data-stu-id="d2bff-111">Required.</span></span> <span data-ttu-id="d2bff-112">Un nombre de tipo que se puede resolver en nombres XAML predeterminado actual; o especificado asigna prefijo si `prefix` se proporciona.</span><span class="sxs-lookup"><span data-stu-id="d2bff-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2bff-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2bff-113">Remarks</span></span>  
 <span data-ttu-id="d2bff-114">El `x:Type` extensión de marcado tiene una función similar a la `typeof()` operador de C# o `GetType` (operador) en Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d2bff-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>  
  
 <span data-ttu-id="d2bff-115">El `x:Type` extensión de marcado proporciona un comportamiento de conversión de cadena para las propiedades que tenga el tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="d2bff-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="d2bff-116">La entrada es un tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="d2bff-116">The input is a XAML type.</span></span> <span data-ttu-id="d2bff-117">La relación entre el tipo de entrada XAML y la salida CLR <xref:System.Type> que es el resultado <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> de la entrada <xref:System.Xaml.XamlType>, después de buscar el necesario <xref:System.Xaml.XamlType> basándose en el contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver>proporciona el contexto de servicio.</span><span class="sxs-lookup"><span data-stu-id="d2bff-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="d2bff-118">En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.TypeExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="d2bff-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="d2bff-119">En las implementaciones de un marco concreto, algunas propiedades que toman <xref:System.Type> como un valor puede aceptar el nombre del tipo directamente (el valor de cadena del tipo `Name`).</span><span class="sxs-lookup"><span data-stu-id="d2bff-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="d2bff-120">Sin embargo, implementar este comportamiento es un escenario complejo.</span><span class="sxs-lookup"><span data-stu-id="d2bff-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="d2bff-121">Para obtener ejemplos, vea la sección "Notas de uso de WPF" que sigue.</span><span class="sxs-lookup"><span data-stu-id="d2bff-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="d2bff-122">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="d2bff-123">El token de cadena que se proporciona después de la cadena de identificador `x:Type` se asigna como valor de <xref:System.Windows.Markup.TypeExtension.TypeName%2A> de la clase de extensión <xref:System.Windows.Markup.TypeExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="d2bff-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="d2bff-124">En el contexto de esquema XAML predeterminado para servicios de XAML de .NET Framework, que se basa en tipos CLR, el valor de este atributo es el <xref:System.Reflection.MemberInfo.Name%2A> del tipo deseado, o que contiene <xref:System.Reflection.MemberInfo.Name%2A> precedido por un prefijo para un espacio de nombres XAML no predeterminado asignación.</span><span class="sxs-lookup"><span data-stu-id="d2bff-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="d2bff-125">El `x:Type` en la sintaxis de elemento de objeto, se puede utilizar la extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="d2bff-126">En este caso, especificando el valor de la <xref:System.Windows.Markup.TypeExtension.TypeName%2A> propiedad es necesaria para inicializar correctamente la extensión.</span><span class="sxs-lookup"><span data-stu-id="d2bff-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="d2bff-127">El `x:Type` extensión de marcado también puede usarse como un atributo detallado; sin embargo este uso no es habitual: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="d2bff-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d2bff-128">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="d2bff-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="d2bff-129">Namespace XAML y asignación de tipos predeterminados</span><span class="sxs-lookup"><span data-stu-id="d2bff-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="d2bff-130">Espacio de nombres XAML predeterminado para la programación de WPF contiene la mayoría de los tipos XAML que necesario para los escenarios típicos de XAML; por lo tanto, se pueden evitar a menudo los prefijos al hacer referencia a valores de tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="d2bff-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="d2bff-131">Debe asignar un prefijo si hace referencia a un tipo de un ensamblado personalizado o para los tipos que existen en un ensamblado WPF pero proceden de un espacio de nombres CLR que no se ha asignado al espacio de nombres XAML predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="d2bff-132">Para obtener más información acerca de los prefijos y espacios de nombres XAML, los espacios de nombres CLR de asignación, consulte [espacios de nombres XAML y asignación de Namespace para XAML de WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d2bff-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="d2bff-133">Propiedades esa compatibilidad Typename como cadena de tipo</span><span class="sxs-lookup"><span data-stu-id="d2bff-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="d2bff-134">WPF admite técnicas que permiten especificar el valor de algunas propiedades de tipo <xref:System.Type> sin necesidad de un `x:Type` uso de la extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="d2bff-135">En su lugar, puede especificar el valor como una cadena que designa el tipo.</span><span class="sxs-lookup"><span data-stu-id="d2bff-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="d2bff-136">Ejemplos de esto son <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> y <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d2bff-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d2bff-137">Compatibilidad con este comportamiento no se proporciona a través de las extensiones de marcado o los convertidores de tipos.</span><span class="sxs-lookup"><span data-stu-id="d2bff-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="d2bff-138">En su lugar, esto es un comportamiento del aplazamiento implementado a través de <xref:System.Windows.FrameworkElementFactory>.</span><span class="sxs-lookup"><span data-stu-id="d2bff-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="d2bff-139">Silverlight admite la convención similar.</span><span class="sxs-lookup"><span data-stu-id="d2bff-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="d2bff-140">De hecho, Silverlight no admite actualmente la `{x:Type}` en su compatibilidad de lenguaje XAML y no acepta `{x:Type}` usos fuera algunas circunstancias que están diseñados para admitir la migración de XAML de WPF y Silverlight.</span><span class="sxs-lookup"><span data-stu-id="d2bff-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="d2bff-141">Por lo tanto, el comportamiento de typename como cadena está integrado para la evaluación de propiedades nativas de Silverlight todos los donde un <xref:System.Type> es el valor.</span><span class="sxs-lookup"><span data-stu-id="d2bff-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="d2bff-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="d2bff-142">XAML 2009</span></span>  
 <span data-ttu-id="d2bff-143">XAML 2009 proporciona compatibilidad adicional para tipos de genéricos y modifica el comportamiento de la característica de `x:TypeArguments` y `x:Type` para proporcionar esta compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d2bff-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   <span data-ttu-id="d2bff-144">`x:TypeArguments` y el elemento de objeto asociado para la creación de instancias de un objeto genérico puede estar en elementos distintos de la raíz.</span><span class="sxs-lookup"><span data-stu-id="d2bff-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="d2bff-145">Para obtener más información, vea la sección "XAML 2009" de [x: TypeArguments (directiva)](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span><span class="sxs-lookup"><span data-stu-id="d2bff-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="d2bff-146">XAML 2009 admite una sintaxis para especificar la restricción de un tipo genérico en el marcado.</span><span class="sxs-lookup"><span data-stu-id="d2bff-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="d2bff-147">Esto se puede utilizar por `x:TypeArguments`, `x:Type`, o las dos características en combinación.</span><span class="sxs-lookup"><span data-stu-id="d2bff-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="d2bff-148">Implementación de XAML de WPF al procesar XAML 2009 para carga también agrega esta capacidad para el comportamiento de conversión de tipos implícita para ciertas propiedades de marco de trabajo que utilizan tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="d2bff-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="d2bff-149">En WPF, puede usar características de XAML 2009 pero solo para XAML dinámico (XAML que no está compilado por marcado).</span><span class="sxs-lookup"><span data-stu-id="d2bff-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="d2bff-150">XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="d2bff-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bff-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2bff-151">See Also</span></span>  
 <xref:System.Windows.Style>  
 [<span data-ttu-id="d2bff-152">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="d2bff-152">Styling and Templating</span></span>](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d2bff-153">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d2bff-153">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="d2bff-154">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="d2bff-154">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
