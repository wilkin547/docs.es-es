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
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484706"
---
# <a name="xnull-markup-extension"></a>x:Null (Extensión de marcado)
Especifica `null` como un valor para un miembro XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave para una referencia nula C# en C++ y es NULL. La palabra clave de Microsoft Visual Basic para una referencia `Nothing`nula es, pero siempre `{x:Null}` se usa como el uso de XAML independientemente del lenguaje de código subyacente que se asocie a XAML.  
  
 La `x:Null` extensión de marcado no tiene propiedades que se puedan establecer.  
  
 Un uso nulo suele estar asociado a la exposición de miembro XAML de un <xref:System.Nullable%601> valor CLR.  
  
 La `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML,`{,}`utiliza llaves () para escapar el control de los valores de atributo para que no sean literales o referencias del controlador de eventos. La sintaxis de atributo es la sintaxis que se usa con más frecuencia con esta extensión de marcado. Técnicamente, una sintaxis `<x:Null />` de elementos de objeto es posible, pero rara vez `x:Null` se usa porque la extensión de marcado no tiene ningún parámetro posicional o de construcción.  
  
 Para obtener información sobre las extensiones de marcado, vea [extensiones de marcado y XAML de WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 En .NET Framework servicios XAML, la <xref:System.Windows.Markup.NullExtension> clase define el control para esta extensión de marcado.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 Tenga en `null` cuenta que no es necesariamente el valor no establecido inicial para una propiedad de dependencia de tipo de referencia. El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en metadatos específicos de la propiedad. Muchas propiedades de dependencia no aceptan `null` como valor, ya sea a través de marcado o código debido a sus implementaciones de devolución de llamada de validación. Para obtener más información sobre las propiedades de dependencia, consulte [información general sobre las propiedades de dependencia](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
