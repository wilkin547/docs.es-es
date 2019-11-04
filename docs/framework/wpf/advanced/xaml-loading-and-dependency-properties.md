---
title: Carga de XAML y propiedades de dependencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: 57c25297f995acd1ef307466258b5f4e03cc3098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459535"
---
# <a name="xaml-loading-and-dependency-properties"></a>Carga de XAML y propiedades de dependencia
Tener en cuenta las propiedades de dependencia es inherente a la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. El procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa métodos del sistema de propiedades para las propiedades de dependencia al cargar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario y al procesar atributos que son propiedades de dependencia. En la práctica esto supone la omisión de los contenedores de propiedad. Cuando implemente propiedades de dependencia personalizadas, debe tener en cuenta este comportamiento y evitar colocar cualquier otro código en el contenedor de propiedades que no sea los métodos del sistema de propiedades <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se presupone que comprende las propiedades de dependencia como consumidor y como autor, y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md) y [Propiedades de dependencia personalizadas](custom-dependency-properties.md). También es conveniente haber leído [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) y [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementación de cargador de XAML de WPF y rendimiento  
 Por motivos de implementación, es económicamente más económico identificar una propiedad como una propiedad de dependencia y tener acceso al método <xref:System.Windows.DependencyObject.SetValue%2A> del sistema de propiedades para establecerla, en lugar de usar el contenedor de propiedades y su establecedor. Esto se debe a que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe deducir el modelo de objetos completo del código de respaldo basándose únicamente en las relaciones entre los miembros y los tipos que se indican en la estructura del marcado y en diversas cadenas.  
  
 El tipo se busca a través de una combinación de xmlns y atributos de ensamblado, pero la identificación de los miembros, la determinación de que podría admitir su establecimiento como atributo y la resolución de los tipos que admiten los valores de propiedad; de lo contrario, requeriría una reflexión extensa uso de <xref:System.Reflection.PropertyInfo>. Dado que las propiedades de dependencia de un tipo determinado son accesibles como una tabla de almacenamiento a través del sistema de propiedades, la implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de su procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utiliza esta tabla e infiere que cualquier propiedad *ABC* determinada puede establecerse de forma más eficaz. llamar a <xref:System.Windows.DependencyObject.SetValue%2A> en el tipo derivado <xref:System.Windows.DependencyObject> derivado mediante el identificador de la propiedad de dependencia *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Implicaciones para las propiedades de dependencia personalizadas  
 Dado que la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamiento del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para establecer propiedades omite completamente los contenedores, no se debe incluir ninguna lógica adicional en las definiciones de conjuntos del contenedor para la propiedad de dependencia personalizada. Si incluye lógica de este tipo en la definición de conjuntos, dicha lógica no se ejecutará cuando la propiedad se establezca en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en lugar de en el código.  
  
 Del mismo modo, otros aspectos del procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que obtienen valores de propiedad del procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también utilizan <xref:System.Windows.DependencyObject.GetValue%2A> en lugar de usar el contenedor. Por lo tanto, también debe evitar cualquier implementación adicional en la definición de `get` más allá de la llamada <xref:System.Windows.DependencyObject.GetValue%2A>.  
  
 El ejemplo siguiente es una definición de propiedad de dependencia recomendada con contenedores, donde el identificador de propiedad está almacenado como un campo `public` `static` `readonly` y las definiciones de `get` y `set` no contienen ningún código excepto los métodos del sistema de propiedades necesarios que definen la lógica de respaldo de las propiedades de dependencia.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md)
- [Seguridad de las propiedades de dependencia](dependency-property-security.md)
- [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
