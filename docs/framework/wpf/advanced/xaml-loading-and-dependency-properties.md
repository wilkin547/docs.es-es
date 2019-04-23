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
ms.openlocfilehash: 4db87c5f266a9eed136f0651f48d11720abede65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083842"
---
# <a name="xaml-loading-and-dependency-properties"></a>Carga de XAML y propiedades de dependencia
Tener en cuenta las propiedades de dependencia es inherente a la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. El procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa métodos del sistema de propiedades para las propiedades de dependencia al cargar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario y al procesar atributos que son propiedades de dependencia. En la práctica esto supone la omisión de los contenedores de propiedad. Al implementar propiedades de dependencia personalizadas, debe tener en cuenta para este comportamiento y debe evitar colocar cualquier otro código en el contenedor de propiedad que no sean los métodos de propiedad del sistema <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se presupone que comprende las propiedades de dependencia como consumidor y como autor, y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md) y [Propiedades de dependencia personalizadas](custom-dependency-properties.md). También es conveniente haber leído [Información general sobre XAML (WPF)](xaml-overview-wpf.md) y [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementación de cargador de XAML de WPF y rendimiento  
 Por motivos de implementación, es menos cara a identificar una propiedad como una propiedad de dependencia y tener acceso al sistema de propiedad <xref:System.Windows.DependencyObject.SetValue%2A> método para establecer, en lugar de utilizar el contenedor de propiedad y su establecedor. Esto se debe a que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe deducir el modelo de objetos completo del código de respaldo basándose únicamente en las relaciones entre los miembros y los tipos que se indican en la estructura del marcado y en diversas cadenas.  
  
 El tipo se busca mediante una combinación de xmlns y atributos de ensamblado, pero para identificar a los miembros, determinar cuáles admiten que se establece como un atributo, y resolver qué tipos admiten los valores de propiedad en caso contrario, podría requerir una extensa reflexión uso de <xref:System.Reflection.PropertyInfo>. Porque las propiedades de dependencia en un tipo determinado son accesibles como una tabla de almacenamiento a través del sistema de propiedad, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación de su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador utiliza esta tabla y deduce que cualquier propiedad especificada *ABC* se puede establecer de forma más eficaz mediante una llamada a <xref:System.Windows.DependencyObject.SetValue%2A> en el que contiene <xref:System.Windows.DependencyObject> tipo derivado, utilizando el identificador de propiedad de dependencia *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Implicaciones para las propiedades de dependencia personalizadas  
 Dado que la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamiento del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para establecer propiedades omite completamente los contenedores, no se debe incluir ninguna lógica adicional en las definiciones de conjuntos del contenedor para la propiedad de dependencia personalizada. Si incluye lógica de este tipo en la definición de conjuntos, dicha lógica no se ejecutará cuando la propiedad se establezca en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en lugar de en el código.  
  
 De forma similar, otros aspectos de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador que obtienen valores de propiedad de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también uso el procesamiento <xref:System.Windows.DependencyObject.GetValue%2A> en lugar del contenedor. Por lo tanto, también debe evitar cualquier implementación adicional en el `get` definición más allá de la <xref:System.Windows.DependencyObject.GetValue%2A> llamar.  
  
 El ejemplo siguiente es una definición de propiedad de dependencia recomendada con contenedores, donde el identificador de propiedad está almacenado como un campo `public` `static` `readonly` y las definiciones de `get` y `set` no contienen ningún código excepto los métodos del sistema de propiedades necesarios que definen la lógica de respaldo de las propiedades de dependencia.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Propiedades de dependencia de tipo de colección](collection-type-dependency-properties.md)
- [Seguridad de las propiedades de dependencia](dependency-property-security.md)
- [Modelos de constructores seguros para objetos DependencyObject](safe-constructor-patterns-for-dependencyobjects.md)
