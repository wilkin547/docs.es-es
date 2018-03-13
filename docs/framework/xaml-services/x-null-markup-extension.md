---
title: "x:Null (Extensión de marcado)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- Null
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b10d759a4f79eabe973a0fcd60736428e46f659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xnull-markup-extension"></a>x:Null (Extensión de marcado)
Especifica `null` como un valor para un miembro XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave para una referencia nula en [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] es null. El [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] palabra clave para una referencia nula es `Nothing`, pero siempre utilizar `{x:Null}` como el uso XAML sin tener en cuenta qué lenguaje de código subyacente se asocia con el código XAML.  
  
 El `x:Null` extensión de marcado no tiene ninguna propiedad configurable.  
  
 Un uso null a menudo está asociado a la exposición de miembro XAML de un CLR <xref:System.Nullable%601> valor.  
  
 El `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML, utiliza las llaves (`{,}`) para la administración de los valores de atributo de literales o referencias de controlador de eventos de secuencia de escape. La sintaxis de atributo es la sintaxis que se usan con mayor frecuencia con esta extensión de marcado. Una sintaxis de elemento de objeto `<x:Null />` es técnicamente posible, pero se usa con poca frecuencia porque el `x:Null` extensión de marcado no tiene parámetros posicionales o argumentos de construcción.  
  
 Para obtener información acerca de las extensiones de marcado, vea [las extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.NullExtension> clase.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Tenga en cuenta que `null` no es necesariamente el valor inicial no establecido para una propiedad de dependencia de tipo de referencia. El valor predeterminado inicial puede variar para cada propiedad de dependencia y se puede basar en metadatos específicos de la propiedad. Muchas propiedades de dependencia no aceptan `null` como un valor, ya sea a través de marcado o el código debido a sus implementaciones de devolución de llamada de validación. Para obtener más información acerca de las propiedades de dependencia, vea [información general sobre propiedades de dependencia](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
