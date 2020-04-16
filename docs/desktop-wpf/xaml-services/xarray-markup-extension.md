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
# <a name="xarray-markup-extension"></a>x:Array (Extensión de marcado)

Proporciona compatibilidad general para matrices de objetos en XAML a través de una extensión de marcado. Esto corresponde al `x:ArrayExtension` tipo XAML en [MS-XAML].

## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`typeName`|El nombre del tipo `x:Array` que contendrá. `typeName`puede tener (y a menudo lo es) el prefijo de un espacio de nombres XAML que contiene las definiciones de tipo XAML.|
|`arrayContents`|El contenido de los elementos que se asigna a la propiedad intrínseca. `ArrayExtension.Items` Normalmente, estos elementos se especifican como uno o `x:Array` varios elementos de objeto contenidos en las etiquetas de apertura y cierre. Se espera que los objetos especificados aquí sean `typeName`asignables al tipo XAML especificado en .|

## <a name="remarks"></a>Observaciones

`Type`es un atributo `x:Array` obligatorio para todos los elementos de objeto. Un `Type` valor de parámetro no `x:Type` necesita usar una extensión de marcado; el nombre corto del tipo es un tipo XAML, que se puede especificar como una cadena.

En la implementación de Servicios XAML de .NET, <xref:System.Type> la relación entre el tipo XAML de entrada y el CLR de salida de la matriz creada se ve influenciada por el contexto de servicio para las extensiones de marcado. La <xref:System.Type> salida <xref:System.Xaml.XamlType.UnderlyingType%2A> es el tipo XAML de entrada, después de buscar lo necesario <xref:System.Xaml.XamlType> en función del contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver> servicio que proporciona el contexto.

Cuando se procesa, el contenido `ArrayExtension.Items` de la matriz se asigna a la propiedad intrínseca. En <xref:System.Windows.Markup.ArrayExtension> la implementación, esto <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>se representa mediante .

En la implementación de servicios XAML de .NET, la <xref:System.Windows.Markup.ArrayExtension> clase define el control de esta extensión de marcado. <xref:System.Windows.Markup.ArrayExtension>no está sellado y podría usarse como base para una implementación de extensión de marcado para un tipo de matriz personalizada.

`x:Array`está más diseñado para la extensibilidad general del lenguaje en XAML. Pero `x:Array` también puede ser útil para especificar valores XAML de ciertas propiedades que toman colecciones compatibles con XAML como su contenido de propiedad estructurada. Por ejemplo, podría especificar el <xref:System.Collections.IEnumerable> contenido `x:Array` de una propiedad con un uso.

`x:Array` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. `x:Array`es parcialmente una excepción a esa regla `x:Array` porque en lugar de proporcionar un control de valor de atributo alternativo, proporciona un control alternativo de su contenido de texto interno. Este comportamiento permite que los tipos que podrían no ser compatibles con un modelo de contenido existente se agrupen en una matriz y se haga referencia más adelante en el código subyacente mediante el acceso a la matriz con nombre; puede llamar <xref:System.Array> a métodos para obtener elementos de matriz individuales.

Todas las extensiones de marcado{,} `)` en XAML usan las llaves (en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el valor del atributo. Para obtener más información acerca de las extensiones de marcado en general, vea convertidores de tipos [y extensiones](type-converters-and-markup-extensions.md)de marcado para XAML .

En XAML 2009, `x:Array` se define como una primitiva de lenguaje en lugar de una extensión de marcado. Para obtener más información, vea [Tipos integrados para primitivas](types-for-primitives.md)de lenguaje XAML comunes .

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

Normalmente, los elementos `x:Array` de objeto que rellenan un no son elementos que existen en el [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres XAML y requieren una asignación de prefijo a un espacio de nombres XAML no predeterminado.

Por ejemplo, la siguiente es una matriz `sys` simple de `x`dos cadenas, con el prefijo (y también) definido en el nivel de la matriz.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

Para los tipos personalizados que se usan como elementos de matriz, la clase también debe admitir los requisitos para crear instancias en XAML como elementos de objeto. Para obtener más información, vea [XAML y clases personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).

## <a name="see-also"></a>Consulte también

- [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Tipos migrados de WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
