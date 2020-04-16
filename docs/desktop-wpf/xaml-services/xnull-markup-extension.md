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
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432699"
---
# <a name="xnull-markup-extension"></a>x:Null (Extensión de marcado)

Especifica `null` como un valor para un miembro XAML.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>Observaciones

La palabra clave para una referencia nula en C- y C++ es null. La palabra clave de Microsoft `Nothing`Visual Basic para `{x:Null}` una referencia nula es , pero siempre se usa como el uso XAML independientemente del lenguaje de código subyacente que asocie con el XAML.

La `x:Null` extensión de marcado no tiene propiedades configurables.

Un uso nulo a menudo se asocia <xref:System.Nullable%601> con la exposición de miembroXAML de un valor CLR.

La `x:Null` extensión de marcado, como todas las`{,}`extensiones de marcado XAML, usa las llaves ( ) para escapar del control de los valores de atributo que no sean literales o referencias de controlador de eventos. Sintaxis de atributo es la sintaxis más utilizada con esta extensión de marcado. Una sintaxis `<x:Null />` de elemento de objeto es técnicamente posible, pero rara vez se utiliza porque la `x:Null` extensión de marcado no tiene parámetros posicionales ni argumentos de construcción.

Para obtener información acerca de las extensiones de marcado, vea [Extensiones](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)de marcado y XAML de WPF .

En los servicios XAML de .NET, la <xref:System.Windows.Markup.NullExtension> clase define el control de esta extensión de marcado.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

Tenga `null` en cuenta que no es necesariamente el valor inicial de unset para una propiedad de dependencia de tipo de referencia. El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en metadatos específicos de la propiedad. Muchas propiedades de `null` dependencia no se aceptan como un valor, ya sea a través de marcado o código debido a sus implementaciones de devolución de llamada de validación. Para obtener más información acerca de las propiedades de dependencia, vea [Información general sobre propiedades](../../framework/wpf/advanced/dependency-properties-overview.md)de dependencia .

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
