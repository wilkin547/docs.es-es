---
title: "Carga de XAML y propiedades de dependencia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "propiedades de dependencia personalizadas"
  - "propiedades de dependencia, cargar XAML y"
  - "cargar datos XML"
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Carga de XAML y propiedades de dependencia
Tener en cuenta las propiedades de dependencia es inherente a la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  El procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza métodos del sistema de propiedades para las propiedades de dependencia al cargar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] binario y al procesar atributos que son propiedades de dependencia.  En la práctica esto supone la omisión de los contenedores de propiedad.  Al implementar propiedades de dependencia personalizadas, debe tener en cuenta este comportamiento y evitar incluir en el contenedor de propiedad ningún código que no sean los métodos del sistema de propiedades <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se supone que el lector comprende las propiedades de dependencia como consumidor y como autor, y que ha leído los artículos [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) y [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  También es conveniente haber leído [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) y [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## Implementación de cargador de XAML de WPF y rendimiento  
 Por motivos de implementación, resulta menos costoso desde el punto de vista de la informática identificar una propiedad como de dependencia y tener acceso al método <xref:System.Windows.DependencyObject.SetValue%2A> del sistema de propiedades para establecerla, en lugar de utilizar el contenedor de propiedad y su establecedor.  Esto se debe a que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe deducir el modelo de objetos completo del código de respaldo basándose únicamente en las relaciones entre los miembros y los tipos que se indican en la estructura del marcado y en diversas cadenas.  
  
 El tipo se busca mediante una combinación de xmlns y atributos de ensamblado, pero para identificar los miembros, determinar cuáles admiten que se los establezca como atributos, y resolver qué tipos admiten los valores de propiedad, se requeriría llevar a cabo una extensa reflexión mediante <xref:System.Reflection.PropertyInfo>.  Dado que las propiedades de dependencia de un tipo determinado están accesibles como una tabla de almacenamiento a través del sistema de propiedades, la implementación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utiliza esta tabla y deduce que cualquier propiedad *ABC* determinada se puede establecer de un modo más eficaz llamando al método <xref:System.Windows.DependencyObject.SetValue%2A> del tipo derivado contenedor <xref:System.Windows.DependencyObject>, para lo que se utiliza el identificador de propiedad de dependencia *ABCPropiedad*.  
  
<a name="implications"></a>   
## Implicaciones para las propiedades de dependencia personalizadas  
 Dado que la implementación actual en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del comportamiento del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para establecer propiedades omite completamente los contenedores, no se debe incluir ninguna lógica adicional en las definiciones de conjuntos del contenedor para la propiedad de dependencia personalizada.  Si incluye lógica de este tipo en la definición de conjuntos, dicha lógica no se ejecutará cuando la propiedad se establezca en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en lugar de mediante código.  
  
 De igual forma, otros aspectos del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que obtienen valores de propiedades del procesamiento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también utilizan <xref:System.Windows.DependencyObject.GetValue%2A> en lugar del contenedor.  Por consiguiente, también se debe evitar cualquier implementación adicional en la definición de `get` que no sea la llamada a <xref:System.Windows.DependencyObject.GetValue%2A>.  
  
 El ejemplo siguiente es una definición de propiedad de dependencia recomendada con contenedores, donde el identificador de propiedad está almacenado como un campo `public``static``readonly` y las definiciones de `set` y `get` no contienen ningún código excepto los métodos del sistema de propiedades necesarios que definen la lógica de respaldo de las propiedades de dependencia.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Propiedades de dependencia de tipo de colección](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [Modelos de constructores seguros para objetos DependencyObject](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)