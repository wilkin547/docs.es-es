---
title: Extensiones de marcado x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433269"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="69fee-102">Extensiones de marcado x:Static</span><span class="sxs-lookup"><span data-stu-id="69fee-102">x:Static Markup Extension</span></span>

<span data-ttu-id="69fee-103">Hace referencia a cualquier entidad de código estático por valor que se define de forma compatible con Common Language Specification (CLS).</span><span class="sxs-lookup"><span data-stu-id="69fee-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="69fee-104">La propiedad estática a la que se hace referencia se puede usar para proporcionar el valor de una propiedad en XAML.</span><span class="sxs-lookup"><span data-stu-id="69fee-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="69fee-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="69fee-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="69fee-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="69fee-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="69fee-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69fee-107">Optional.</span></span> <span data-ttu-id="69fee-108">Prefijo que hace referencia a un espacio de nombres XAML asignado y no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="69fee-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="69fee-109">`prefix`se muestra explícitamente en el uso porque rara vez se hace referencia a propiedades estáticas que proceden de un espacio de nombres XAML predeterminado.</span><span class="sxs-lookup"><span data-stu-id="69fee-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="69fee-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="69fee-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="69fee-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69fee-111">Required.</span></span> <span data-ttu-id="69fee-112">El nombre del tipo que define el miembro estático deseado.</span><span class="sxs-lookup"><span data-stu-id="69fee-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="69fee-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69fee-113">Required.</span></span> <span data-ttu-id="69fee-114">El nombre del miembro de valor estático deseado (una constante, una propiedad estática, un campo o un valor de enumeración).</span><span class="sxs-lookup"><span data-stu-id="69fee-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="69fee-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69fee-115">Remarks</span></span>

<span data-ttu-id="69fee-116">La entidad de código a la que se hace referencia debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="69fee-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="69fee-117">Una constante</span><span class="sxs-lookup"><span data-stu-id="69fee-117">A constant</span></span>
- <span data-ttu-id="69fee-118">Una propiedad estática</span><span class="sxs-lookup"><span data-stu-id="69fee-118">A static property</span></span>
- <span data-ttu-id="69fee-119">Un campo</span><span class="sxs-lookup"><span data-stu-id="69fee-119">A field</span></span>
- <span data-ttu-id="69fee-120">Un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="69fee-120">An enumeration value</span></span>

<span data-ttu-id="69fee-121">Especificar cualquier otra entidad de código, como una propiedad no estática, produce un error en tiempo de compilación si el XAML está compilado de marcado o una excepción de análisis en tiempo de carga XAML.</span><span class="sxs-lookup"><span data-stu-id="69fee-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="69fee-122">Puede hacer `x:Static` referencias a campos estáticos o propiedades que no están en el espacio de nombres XAML predeterminado para el documento XAML actual; sin embargo, esto requiere una asignación de prefijo.</span><span class="sxs-lookup"><span data-stu-id="69fee-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="69fee-123">Los espacios de nombres XAML casi siempre se definen en el elemento raíz del documento XAML.</span><span class="sxs-lookup"><span data-stu-id="69fee-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="69fee-124">Las operaciones de búsqueda de propiedades estáticas las pueden realizar los servicios XAML de .NET y sus lectores XAML y escritores XAML, cuando se ejecutan con el contexto de esquema XAML predeterminado.</span><span class="sxs-lookup"><span data-stu-id="69fee-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="69fee-125">Este contexto de esquema XAML puede usar la reflexión CLR para proporcionar los valores estáticos necesarios para la construcción de gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="69fee-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="69fee-126">El `typeName` especificar es en realidad un nombre de tipo XAML, no un nombre de tipo CLR, aunque estos son esencialmente el mismo nombre cuando se usa el contexto de esquema XAML predeterminado o cuando se usan todos los marcos de implementación XAML basados en CLR existentes.</span><span class="sxs-lookup"><span data-stu-id="69fee-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="69fee-127">Tenga cuidado al `x:Static` crear referencias que no son directamente el tipo del valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="69fee-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="69fee-128">En la secuencia de procesamiento XAML, los valores proporcionados de una extensión de marcado no invocan la conversión de valores adicionales.</span><span class="sxs-lookup"><span data-stu-id="69fee-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="69fee-129">Esto es cierto `x:Static` incluso si la referencia crea una cadena de texto y una conversión de valor para los valores de atributo basados en la cadena de texto normalmente se produce para ese miembro específico o para cualquier valor de miembro del tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="69fee-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="69fee-130">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="69fee-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="69fee-131">El token de cadena que se proporciona después de la cadena de identificador `x:Static` se asigna como valor de <xref:System.Windows.Markup.StaticExtension.Member%2A> de la clase de extensión <xref:System.Windows.Markup.StaticExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="69fee-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="69fee-132">Hay otros dos usos XAML que son técnicamente posibles.</span><span class="sxs-lookup"><span data-stu-id="69fee-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="69fee-133">Sin embargo, estos usos son menos comunes porque son innecesariamente detallados:</span><span class="sxs-lookup"><span data-stu-id="69fee-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="69fee-134">Sintaxis de elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="69fee-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="69fee-135">Sintaxis de atributo con propiedad Member explícita para la cadena de inicialización.</span><span class="sxs-lookup"><span data-stu-id="69fee-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="69fee-136">En la implementación de servicios XAML de .NET, la <xref:System.Windows.Markup.StaticExtension> clase define el control de esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="69fee-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="69fee-137">`x:Static` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="69fee-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="69fee-138">Todas las extensiones `{` de `}` marcado en XAML usan los caracteres y en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="69fee-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="69fee-139">Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="69fee-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="69fee-140">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="69fee-140">WPF Usage Notes</span></span>

<span data-ttu-id="69fee-141">El espacio de nombres XAML predeterminado que se usa para la programación WPFWPF no contiene muchas propiedades estáticas `{x:Static}` útiles y la mayoría de las propiedades estáticas útiles tienen compatibilidad, como convertidores de tipos que facilitan el uso sin necesidad de .</span><span class="sxs-lookup"><span data-stu-id="69fee-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="69fee-142">Para las propiedades estáticas, debe asignar un prefijo para un espacio de nombres XAML si se cumple una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="69fee-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="69fee-143">Hace referencia a un tipo que existe en WPFWPF pero no`http://schemas.microsoft.com/winfx/2006/xaml/presentation`forma parte del espacio de nombres XAML predeterminado para WPF ( ).</span><span class="sxs-lookup"><span data-stu-id="69fee-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="69fee-144">Este es un escenario `x:Static`bastante común para usar .</span><span class="sxs-lookup"><span data-stu-id="69fee-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="69fee-145">Por ejemplo, puede `x:Static` usar una referencia con <xref:System> una asignación de espacio de nombres XAML al <xref:System.Environment> espacio de nombres CLR y al ensamblado mscorlib para hacer referencia a las propiedades estáticas de la clase.</span><span class="sxs-lookup"><span data-stu-id="69fee-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="69fee-146">Hace referencia a un tipo de un ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="69fee-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="69fee-147">Hace referencia a un tipo que existe en un ensamblado WPFWPF, pero ese tipo está dentro de un espacio de nombres CLR que no se asignó para formar parte del espacio de nombres XAML predeterminado de WPF.</span><span class="sxs-lookup"><span data-stu-id="69fee-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="69fee-148">La asignación de espacios de nombres CLR en el espacio de nombres XAML predeterminado para WPFWPF se realiza mediante definiciones en los distintos ensamblados de WPF (para obtener más información acerca de este concepto, vea [Espacios de nombres XAML y Asignación](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF).</span><span class="sxs-lookup"><span data-stu-id="69fee-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="69fee-149">Los espacios de nombres CLR no asignados pueden existir si ese espacio de nombres CLR <xref:System.Windows.Threading>se compone principalmente de definiciones de clase que normalmente no están destinadas a XAML, como .</span><span class="sxs-lookup"><span data-stu-id="69fee-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="69fee-150">Para obtener más información sobre cómo usar prefijos y espacios de nombres XAML para WPF, vea [Espacios de nombres XAML y Asignación](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF .</span><span class="sxs-lookup"><span data-stu-id="69fee-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69fee-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69fee-151">See also</span></span>

- [<span data-ttu-id="69fee-152">x:Type (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="69fee-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="69fee-153">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="69fee-153">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
