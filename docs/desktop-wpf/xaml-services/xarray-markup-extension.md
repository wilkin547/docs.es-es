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
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433287"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="b7723-102">x:Array (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="b7723-102">x:Array Markup Extension</span></span>

<span data-ttu-id="b7723-103">Proporciona compatibilidad general para matrices de objetos en XAML a través de una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="b7723-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="b7723-104">Esto corresponde al `x:ArrayExtension` tipo XAML en [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="b7723-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b7723-105">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="b7723-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="b7723-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="b7723-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="b7723-107">El nombre del tipo `x:Array` que contendrá.</span><span class="sxs-lookup"><span data-stu-id="b7723-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="b7723-108">`typeName`puede tener (y a menudo lo es) el prefijo de un espacio de nombres XAML que contiene las definiciones de tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="b7723-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="b7723-109">El contenido de los elementos que se asigna a la propiedad intrínseca. `ArrayExtension.Items`</span><span class="sxs-lookup"><span data-stu-id="b7723-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="b7723-110">Normalmente, estos elementos se especifican como uno o `x:Array` varios elementos de objeto contenidos en las etiquetas de apertura y cierre.</span><span class="sxs-lookup"><span data-stu-id="b7723-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="b7723-111">Se espera que los objetos especificados aquí sean `typeName`asignables al tipo XAML especificado en .</span><span class="sxs-lookup"><span data-stu-id="b7723-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b7723-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7723-112">Remarks</span></span>

<span data-ttu-id="b7723-113">`Type`es un atributo `x:Array` obligatorio para todos los elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="b7723-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="b7723-114">Un `Type` valor de parámetro no `x:Type` necesita usar una extensión de marcado; el nombre corto del tipo es un tipo XAML, que se puede especificar como una cadena.</span><span class="sxs-lookup"><span data-stu-id="b7723-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="b7723-115">En la implementación de Servicios XAML de .NET, <xref:System.Type> la relación entre el tipo XAML de entrada y el CLR de salida de la matriz creada se ve influenciada por el contexto de servicio para las extensiones de marcado.</span><span class="sxs-lookup"><span data-stu-id="b7723-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="b7723-116">La <xref:System.Type> salida <xref:System.Xaml.XamlType.UnderlyingType%2A> es el tipo XAML de entrada, después de buscar lo necesario <xref:System.Xaml.XamlType> en función del contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver> servicio que proporciona el contexto.</span><span class="sxs-lookup"><span data-stu-id="b7723-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="b7723-117">Cuando se procesa, el contenido `ArrayExtension.Items` de la matriz se asigna a la propiedad intrínseca.</span><span class="sxs-lookup"><span data-stu-id="b7723-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="b7723-118">En <xref:System.Windows.Markup.ArrayExtension> la implementación, esto <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>se representa mediante .</span><span class="sxs-lookup"><span data-stu-id="b7723-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b7723-119">En la implementación de servicios XAML de .NET, la <xref:System.Windows.Markup.ArrayExtension> clase define el control de esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="b7723-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="b7723-120"><xref:System.Windows.Markup.ArrayExtension>no está sellado y podría usarse como base para una implementación de extensión de marcado para un tipo de matriz personalizada.</span><span class="sxs-lookup"><span data-stu-id="b7723-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="b7723-121">`x:Array`está más diseñado para la extensibilidad general del lenguaje en XAML.</span><span class="sxs-lookup"><span data-stu-id="b7723-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="b7723-122">Pero `x:Array` también puede ser útil para especificar valores XAML de ciertas propiedades que toman colecciones compatibles con XAML como su contenido de propiedad estructurada.</span><span class="sxs-lookup"><span data-stu-id="b7723-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="b7723-123">Por ejemplo, podría especificar el <xref:System.Collections.IEnumerable> contenido `x:Array` de una propiedad con un uso.</span><span class="sxs-lookup"><span data-stu-id="b7723-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="b7723-124">`x:Array` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="b7723-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="b7723-125">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="b7723-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="b7723-126">`x:Array`es parcialmente una excepción a esa regla `x:Array` porque en lugar de proporcionar un control de valor de atributo alternativo, proporciona un control alternativo de su contenido de texto interno.</span><span class="sxs-lookup"><span data-stu-id="b7723-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="b7723-127">Este comportamiento permite que los tipos que podrían no ser compatibles con un modelo de contenido existente se agrupen en una matriz y se haga referencia más adelante en el código subyacente mediante el acceso a la matriz con nombre; puede llamar <xref:System.Array> a métodos para obtener elementos de matriz individuales.</span><span class="sxs-lookup"><span data-stu-id="b7723-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="b7723-128">Todas las extensiones de marcado{,} `)` en XAML usan las llaves (en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="b7723-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="b7723-129">Para obtener más información acerca de las extensiones de marcado en general, vea convertidores de tipos [y extensiones](type-converters-and-markup-extensions.md)de marcado para XAML .</span><span class="sxs-lookup"><span data-stu-id="b7723-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="b7723-130">En XAML 2009, `x:Array` se define como una primitiva de lenguaje en lugar de una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="b7723-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="b7723-131">Para obtener más información, vea [Tipos integrados para primitivas](types-for-primitives.md)de lenguaje XAML comunes .</span><span class="sxs-lookup"><span data-stu-id="b7723-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="b7723-132">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="b7723-132">WPF Usage Notes</span></span>

<span data-ttu-id="b7723-133">Normalmente, los elementos `x:Array` de objeto que rellenan un no son elementos que existen en el [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres XAML y requieren una asignación de prefijo a un espacio de nombres XAML no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b7723-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="b7723-134">Por ejemplo, la siguiente es una matriz `sys` simple de `x`dos cadenas, con el prefijo (y también) definido en el nivel de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b7723-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="b7723-135">Para los tipos personalizados que se usan como elementos de matriz, la clase también debe admitir los requisitos para crear instancias en XAML como elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="b7723-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="b7723-136">Para obtener más información, vea [XAML y clases personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="b7723-136">For more information, see [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7723-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7723-137">See also</span></span>

- [<span data-ttu-id="b7723-138">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="b7723-138">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="b7723-139">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="b7723-139">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
