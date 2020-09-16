---
title: x:Null (Extensión de marcado)
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: f4971d61d11ec14eaeac2d2f202353e4921b9325
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549449"
---
# <a name="xnull-markup-extension"></a>x:Null (Extensión de marcado)

Especifica `null` como un valor para un miembro XAML.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Comentarios

La palabra clave para una referencia nula en C# y C++ es NULL. La palabra clave de Microsoft Visual Basic para una referencia nula es `Nothing` , pero siempre se usa `{x:Null}` como el uso de XAML independientemente del lenguaje de código subyacente que se ASOCIE a XAML.

La `x:Null` extensión de marcado no tiene propiedades que se puedan establecer.

Un uso nulo suele estar asociado a la exposición de miembro XAML de un <xref:System.Nullable%601> valor CLR.

La `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML, utiliza llaves ( `{,}` ) para escapar el control de los valores de atributo para que no sean literales o referencias del controlador de eventos. La sintaxis de atributo es la sintaxis que se usa con más frecuencia con esta extensión de marcado. Técnicamente, una sintaxis de elementos `<x:Null />` de objeto es posible, pero rara vez se usa porque la `x:Null` extensión de marcado no tiene ningún parámetro posicional o de construcción.

Para obtener información sobre las extensiones de marcado, vea [extensiones de marcado y XAML de WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).

En los servicios XAML de .NET, el control de esta extensión de marcado se define mediante la <xref:System.Windows.Markup.NullExtension> clase.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

Tenga en cuenta que `null` no es necesariamente el valor no establecido inicial para una propiedad de dependencia de tipo de referencia. El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en metadatos específicos de la propiedad. Muchas propiedades de dependencia no aceptan `null` como valor, ya sea a través de marcado o código debido a sus implementaciones de devolución de llamada de validación. Para obtener más información sobre las propiedades de dependencia, vea [Introducción a las propiedades de dependencia](/dotnet/desktop/wpf/advanced/dependency-properties-overview).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
