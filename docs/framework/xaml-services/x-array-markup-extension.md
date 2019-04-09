---
title: x:Array (Extensión de marcado)
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: 4f4e26eb3e5ccaf66b2173c7fc9952375c5f2a58
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139144"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="32405-102">x:Array (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="32405-102">x:Array Markup Extension</span></span>
<span data-ttu-id="32405-103">Proporciona compatibilidad general para las matrices de objetos en XAML a través de una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="32405-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="32405-104">Esto corresponde a la `x:ArrayExtension` tipo XAML en [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="32405-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="32405-105">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="32405-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="32405-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="32405-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="32405-107">El nombre del tipo que su `x:Array` contendrá.</span><span class="sxs-lookup"><span data-stu-id="32405-107">The name of the type that your `x:Array` will contain.</span></span> `typeName` <span data-ttu-id="32405-108">puede ser (y a menudo es) como prefijo para un XAML como definiciones de tipo de espacio de nombres que contiene el XAML.</span><span class="sxs-lookup"><span data-stu-id="32405-108">may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="32405-109">El contenido de los elementos que se asigna a la función intrínseca `ArrayExtension.Items` propiedad.</span><span class="sxs-lookup"><span data-stu-id="32405-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="32405-110">Normalmente, estos elementos se especifican como uno o varios elementos de objeto dentro de la `x:Array` de apertura y cierre de las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="32405-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="32405-111">Objetos especificados aquí, se espera que sean asignables al tipo XAML especificado en `typeName`.</span><span class="sxs-lookup"><span data-stu-id="32405-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32405-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32405-112">Remarks</span></span>  
 `Type` <span data-ttu-id="32405-113">es un atributo obligatorio para todos los `x:Array` elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="32405-113">is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="32405-114">Un `Type` el valor del parámetro no es necesario usar un `x:Type` extensión de marcado; el breve nombre del tipo es un tipo XAML, que se puede especificar como una cadena.</span><span class="sxs-lookup"><span data-stu-id="32405-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="32405-115">En la implementación de servicios XAML de .NET Framework, la relación entre el tipo de entrada XAML y la salida CLR <xref:System.Type> de la matriz creada se ve influenciado por el contexto de servicio para las extensiones de marcado.</span><span class="sxs-lookup"><span data-stu-id="32405-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="32405-116">La salida <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> del tipo XAML de entrada, después de buscar el necesario <xref:System.Xaml.XamlType> según el contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver> proporciona el contexto de servicio.</span><span class="sxs-lookup"><span data-stu-id="32405-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="32405-117">Cuando se procesa, el contenido de la matriz se asigna a la `ArrayExtension.Items` propiedad intrínseca.</span><span class="sxs-lookup"><span data-stu-id="32405-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="32405-118">En el <xref:System.Windows.Markup.ArrayExtension> implementación, se representa mediante <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="32405-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="32405-119">En la implementación de servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.ArrayExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="32405-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <xref:System.Windows.Markup.ArrayExtension> <span data-ttu-id="32405-120">no está sellada y podría usarse como base para una implementación de extensión de marcado para un tipo de matriz personalizada.</span><span class="sxs-lookup"><span data-stu-id="32405-120">is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 `x:Array` <span data-ttu-id="32405-121">es que más está diseñado para general la extensibilidad de lenguaje en XAML.</span><span class="sxs-lookup"><span data-stu-id="32405-121">is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="32405-122">Pero `x:Array` también puede ser útil para especificar valores XAML de ciertas propiedades que toman colecciones compatibles con XAML como su contenido estructurado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="32405-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="32405-123">Por ejemplo, puede especificar el contenido de un <xref:System.Collections.IEnumerable> propiedad con un `x:Array` uso.</span><span class="sxs-lookup"><span data-stu-id="32405-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 `x:Array` <span data-ttu-id="32405-124">es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="32405-124">is a markup extension.</span></span> <span data-ttu-id="32405-125">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="32405-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> `x:Array` <span data-ttu-id="32405-126">parcialmente es una excepción a esta regla porque en lugar de proporcionar control de valor de atributo alternativo, `x:Array` proporciona un control alternativo de su contenido de texto interno.</span><span class="sxs-lookup"><span data-stu-id="32405-126">is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="32405-127">Este comportamiento permite que los tipos que pueden no ser compatibles con un modelo de contenido existente se agrupan en una matriz y más adelante en el código subyacente al que hace referencia mediante el acceso a la matriz con nombre; puede llamar a <xref:System.Array> métodos para obtener los elementos individuales de la matriz.</span><span class="sxs-lookup"><span data-stu-id="32405-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="32405-128">Todas las extensiones de marcado XAML usan las llaves ({,} `)` en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe procesar el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="32405-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="32405-129">Para obtener más información acerca de las extensiones de marcado en general, consulte [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="32405-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="32405-130">En XAML 2009, `x:Array` se define como un lenguaje primitivo en lugar de una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="32405-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="32405-131">Para obtener más información, consulte [tipos integrados para primitivas del lenguaje XAML común](built-in-types-for-common-xaml-language-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="32405-131">For more information, see [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="32405-132">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="32405-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="32405-133">Normalmente, los elementos de objeto que rellenan una `x:Array` no son elementos que existen en el [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres XAML y requieren una asignación de prefijo para un espacio de nombres XAML no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="32405-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="32405-134">Por ejemplo, la siguiente es una simple matriz de dos cadenas, con el `sys` prefijo (y también `x`) definidos en el nivel de la matriz.</span><span class="sxs-lookup"><span data-stu-id="32405-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="32405-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="32405-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="32405-136">Para los tipos personalizados que se usan como elementos de matriz, la clase también debe admitir los requisitos para que se va a crear una instancia en XAML como elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="32405-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="32405-137">Para obtener más información, consulte [XAML y clases personalizadas para WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="32405-137">For more information, see [XAML and Custom Classes for WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32405-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="32405-138">See also</span></span>

- [<span data-ttu-id="32405-139">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="32405-139">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="32405-140">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="32405-140">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
