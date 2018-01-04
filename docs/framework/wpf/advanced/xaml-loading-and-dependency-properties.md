---
title: Carga de XAML y propiedades de dependencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9771aa05d029603a018e041644ff3e2018e26ca4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-loading-and-dependency-properties"></a>Carga de XAML y propiedades de dependencia
Tener en cuenta las propiedades de dependencia es inherente a la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. El procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa métodos del sistema de propiedades para las propiedades de dependencia al cargar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario y al procesar atributos que son propiedades de dependencia. En la práctica esto supone la omisión de los contenedores de propiedad. Al implementar propiedades de dependencia personalizadas, debe tener en cuenta para este comportamiento y debe evitar colocar cualquier otro código en el contenedor de propiedad distinta a los métodos de sistema de propiedad <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se presupone que comprende las propiedades de dependencia como consumidor y como autor, y que ha leído [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) y [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md). También es conveniente haber leído [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) y [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementación de cargador de XAML de WPF y rendimiento  
 Por razones de implementación, es menos costoso identificar una propiedad como una propiedad de dependencia y tener acceso al sistema de propiedad <xref:System.Windows.DependencyObject.SetValue%2A> método para establecer, en lugar de usar el contenedor de propiedad y el establecedor. Esto se debe a que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe deducir el modelo de objetos completo del código de respaldo basándose únicamente en las relaciones entre los miembros y los tipos que se indican en la estructura del marcado y en diversas cadenas.  
  
 Se busca el tipo a través de una combinación de xmlns y atributos de ensamblado, pero para identificar a los miembros, determinar cuáles admiten que se establece como un atributo, y resolver los tipos que admiten los valores de propiedad en caso contrario, podría requerir extensa reflexión mediante <xref:System.Reflection.PropertyInfo>. Dado que las propiedades de dependencia en un tipo determinado están accesibles como una tabla de almacenamiento a través del sistema de propiedad, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación de su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador utiliza esta tabla y deduce que cualquier dada propiedad *ABC* se puede establecer de forma más eficaz mediante una llamada a <xref:System.Windows.DependencyObject.SetValue%2A> en la que contiene <xref:System.Windows.DependencyObject> tipo derivado, utilizando el identificador de propiedad de dependencia *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Implicaciones para las propiedades de dependencia personalizadas  
 Dado que la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamiento del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para establecer propiedades omite completamente los contenedores, no se debe incluir ninguna lógica adicional en las definiciones de conjuntos del contenedor para la propiedad de dependencia personalizada. Si incluye lógica de este tipo en la definición de conjuntos, dicha lógica no se ejecutará cuando la propiedad se establezca en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en lugar de en el código.  
  
 De forma similar, otros aspectos de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador que obtienen valores de propiedad de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesamiento también utilice <xref:System.Windows.DependencyObject.GetValue%2A> en lugar de usar el contenedor. Por lo tanto, también debería evitar cualquier implementación adicional en el `get` definición más allá de la <xref:System.Windows.DependencyObject.GetValue%2A> llamar.  
  
 El ejemplo siguiente es una definición de propiedad de dependencia recomendada con contenedores, donde el identificador de propiedad está almacenado como un campo `public` `static` `readonly` y las definiciones de `get` y `set` no contienen ningún código excepto los métodos del sistema de propiedades necesarios que definen la lógica de respaldo de las propiedades de dependencia.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Propiedades de dependencia de tipo de colección](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [Modelos de constructores seguros para objetos DependencyObject](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
