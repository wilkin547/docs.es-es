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
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100813"
---
# <a name="xnull-markup-extension"></a>x:Null (Extensión de marcado)
Especifica `null` como un valor para un miembro XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave para una referencia nula en C# y [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] es null. La palabra clave de Microsoft Visual Basic para una referencia nula es `Nothing`, pero siempre usar `{x:Null}` como el uso XAML sin tener en cuenta qué lenguaje de código subyacente asocie con el XAML.  
  
 El `x:Null` extensión de marcado no tiene ninguna propiedad configurable.  
  
 Un uso null suele asociarse con la exposición de miembro XAML de un CLR <xref:System.Nullable%601> valor.  
  
 El `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML, usa las llaves (`{,}`) para el tratamiento de los valores de atributo no es literales o referencias de controlador de eventos de secuencia de escape. Sintaxis de atributo es la sintaxis que se usan frecuentemente con esta extensión de marcado. Una sintaxis de elemento de objeto `<x:Null />` es técnicamente posible, pero rara vez se usa porque el `x:Null` extensión de marcado no tiene parámetros posicionales o argumentos de construcción.  
  
 Para obtener información acerca de las extensiones de marcado, vea [extensiones de marcado y WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.NullExtension> clase.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Tenga en cuenta que `null` no es necesariamente el valor inicial no establecido para una propiedad de dependencia de tipo de referencia. El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en los metadatos específicos de la propiedad. Muchas propiedades de dependencia no los acepta `null` como un valor, ya sea a través de marcado o el código debido a sus implementaciones de devolución de llamada de validación. Para obtener más información acerca de las propiedades de dependencia, consulte [información general sobre las propiedades de dependencia](../wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
