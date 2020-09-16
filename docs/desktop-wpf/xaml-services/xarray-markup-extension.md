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
ms.openlocfilehash: b812939cbaa74576361de534c0d39ba45536cbcf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555177"
---
# <a name="xarray-markup-extension"></a>x:Array (Extensión de marcado)

Proporciona compatibilidad general para matrices de objetos en XAML a través de una extensión de marcado. Esto corresponde al `x:ArrayExtension` tipo XAML en [ms-XAML].

## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`typeName`|Nombre del tipo que contendrá `x:Array` . `typeName` puede ser (y con frecuencia) prefijo para un espacio de nombres XAML que contiene las definiciones de tipo XAML.|
|`arrayContents`|El contenido de los elementos que se asigna a la `ArrayExtension.Items` propiedad intrínseca. Normalmente, estos elementos se especifican como uno o varios elementos de objeto incluidos dentro de las `x:Array` etiquetas de apertura y cierre. Se espera que los objetos especificados aquí se puedan asignar al tipo XAML especificado en `typeName` .|

## <a name="remarks"></a>Comentarios

`Type` es un atributo necesario para todos los `x:Array` elementos de objeto. Un `Type` valor de parámetro no necesita usar una `x:Type` extensión de marcado; el nombre corto del tipo es un tipo XAML, que se puede especificar como una cadena.

En la implementación de servicios XAML de .NET, la relación entre el tipo XAML de entrada y el CLR <xref:System.Type> de salida de la matriz creada se ve afectada por el contexto de servicio para las extensiones de marcado. El resultado <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> del tipo XAML de entrada, después de buscar el necesario <xref:System.Xaml.XamlType> basado en el contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver> servicio que proporciona el contexto.

Cuando se procesa, el contenido de la matriz se asigna a la `ArrayExtension.Items` propiedad intrínseca. En la <xref:System.Windows.Markup.ArrayExtension> implementación de, se representa mediante <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .

En la implementación de servicios XAML de .NET, el control de esta extensión de marcado se define mediante la <xref:System.Windows.Markup.ArrayExtension> clase. <xref:System.Windows.Markup.ArrayExtension> no está sellado y podría usarse como base para una implementación de extensión de marcado para un tipo de matriz personalizado.

`x:Array` está más pensado para la extensibilidad general del lenguaje en XAML. Pero `x:Array` también puede ser útil para especificar valores XAML de ciertas propiedades que aceptan colecciones compatibles con XAML como contenido de la propiedad estructurada. Por ejemplo, puede especificar el contenido de una <xref:System.Collections.IEnumerable> propiedad con un `x:Array` uso.

`x:Array` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. `x:Array` es parcialmente una excepción a esa regla porque en lugar de proporcionar un control de valores de atributo alternativo, `x:Array` proporciona un control alternativo de su contenido de texto interno. Este comportamiento permite que los tipos que podrían no ser compatibles con un modelo de contenido existente se agrupen en una matriz y se haga referencia a ellos posteriormente en el código subyacente mediante el acceso a la matriz con nombre. puede llamar <xref:System.Array> a los métodos para obtener elementos individuales de la matriz.

Todas las extensiones de marcado en XAML usan las llaves ( {,} `)` en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el valor de atributo. Para obtener más información sobre las extensiones de marcado en general, vea [convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions.md).

En XAML 2009, `x:Array` se define como un primitivo del lenguaje en lugar de una extensión de marcado. Para obtener más información, vea [tipos integrados para primitivas comunes del lenguaje XAML](types-for-primitives.md).

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

Normalmente, los elementos de objeto que rellenan una `x:Array` no son elementos que existen en el [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres XAML y requieren una asignación de prefijo a un espacio de nombres XAML no predeterminado.

Por ejemplo, la siguiente es una matriz simple de dos cadenas, con el `sys` prefijo (y también `x` ) definido en el nivel de la matriz.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

En el caso de los tipos personalizados que se usan como elementos de matriz, la clase también debe admitir los requisitos para la creación de instancias en XAML como elementos de objeto. Para obtener más información, vea [XAML y clases personalizadas para WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).

## <a name="see-also"></a>Vea también

- [Extensiones de marcado y XAML de WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [Tipos migrados de WPF a System.Xaml](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
