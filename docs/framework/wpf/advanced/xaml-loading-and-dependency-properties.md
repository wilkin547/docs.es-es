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
ms.openlocfilehash: de8050e582f5b1a5a288c350c179cfa24fb5471c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186250"
---
# <a name="xaml-loading-and-dependency-properties"></a>Carga de XAML y propiedades de dependencia
Tener en cuenta las propiedades de dependencia es inherente a la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador utiliza métodos de sistema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de propiedades para las propiedades de dependencia al cargar atributos binarios y de procesamiento que son propiedades de dependencia. En la práctica esto supone la omisión de los contenedores de propiedad. Al implementar propiedades de dependencia personalizadas, debe tener en cuenta este comportamiento y debe <xref:System.Windows.DependencyObject.GetValue%2A> evitar <xref:System.Windows.DependencyObject.SetValue%2A>colocar cualquier otro código en el contenedor de propiedades que no sean los métodos del sistema de propiedades y .  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se presupone que comprende las propiedades de dependencia como consumidor y como autor, y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md) y [Propiedades de dependencia personalizadas](custom-dependency-properties.md). También es conveniente haber leído [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) y [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementación de cargador de XAML de WPF y rendimiento  
 Por motivos de implementación, es computacionalmente menos costoso identificar <xref:System.Windows.DependencyObject.SetValue%2A> una propiedad como una propiedad de dependencia y tener acceso al método del sistema de propiedades para establecerla, en lugar de usar el contenedor de propiedades y su establecedor. Esto se debe a que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe deducir el modelo de objetos completo del código de respaldo basándose únicamente en las relaciones entre los miembros y los tipos que se indican en la estructura del marcado y en diversas cadenas.  
  
 El tipo se busca a través de una combinación de xmlns y atributos de ensamblado, pero la identificación de los <xref:System.Reflection.PropertyInfo>miembros, determinar qué podría admitir que se establece como un atributo y resolver qué tipos admiten los valores de propiedad requeriría una reflexión extensa mediante . Dado que las propiedades de dependencia de un tipo determinado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] accesibles como una tabla de almacenamiento a través del <xref:System.Windows.DependencyObject.SetValue%2A> sistema de <xref:System.Windows.DependencyObject> propiedades, la implementación de su procesador utiliza esta tabla e deduce que cualquier propiedad determinada *ABC* se puede establecer de forma más eficaz llamando al tipo derivado contenedor, utilizando el identificador de propiedad de dependencia *ABCProperty*.  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>Implicaciones para las propiedades de dependencia personalizadas  
 Dado que la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamiento del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para establecer propiedades omite completamente los contenedores, no se debe incluir ninguna lógica adicional en las definiciones de conjuntos del contenedor para la propiedad de dependencia personalizada. Si incluye lógica de este tipo en la definición de conjuntos, dicha lógica no se ejecutará cuando la propiedad se establezca en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en lugar de en el código.  
  
 De forma similar, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] otros aspectos del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador <xref:System.Windows.DependencyObject.GetValue%2A> que obtienen valores de propiedad del procesamiento también usan en lugar de usar el contenedor. Por lo tanto, también debe `get` evitar cualquier <xref:System.Windows.DependencyObject.GetValue%2A> implementación adicional en la definición más allá de la llamada.  
  
 El ejemplo siguiente es una definición de propiedad de dependencia `public` `static` `readonly` recomendada con `get` contenedores, donde el identificador de propiedad se almacena como un campo y las `set` definiciones no contienen código más allá de los métodos de sistema de propiedades necesarios que definen el respaldo de la propiedad de dependencia.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Consulte también

- [Descripción general de las propiedades de dependencia](dependency-properties-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md)
- [Seguridad de las propiedades de dependencia](dependency-property-security.md)
- [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
