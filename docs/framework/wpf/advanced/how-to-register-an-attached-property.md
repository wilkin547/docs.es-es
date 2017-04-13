---
title: "C&#243;mo: Registrar una propiedad asociada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "propiedades asociadas, registrar"
  - "registrar propiedades adjuntas"
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Registrar una propiedad asociada
En este ejemplo se muestra cómo registrar una [propiedad adjunta](GTMT) y proporcionar descriptores de acceso públicos para que se pueda utilizar la propiedad en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en código.  Las propiedades adjuntas son un concepto de sintaxis definido por [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La mayoría de las propiedades adjuntas para los tipos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también se implementan como [propiedades de dependencia](GTMT).  Puede utilizar las [propiedades de dependencia](GTMT) en cualquier tipo <xref:System.Windows.DependencyObject>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo registrar una propiedad adjunta como una propiedad de dependencia, utilizando el método <xref:System.Windows.DependencyProperty.RegisterAttached%2A>.  La clase de proveedor tiene la opción de proporcionar los metadatos predeterminados para la propiedad que son aplicables cuando la propiedad se utiliza en otra clase, a menos que esa clase invalide los metadatos.  En este ejemplo, el valor predeterminado de la propiedad `IsBubbleSource` se establece en `false`.  
  
 La clase de proveedor para una propiedad adjunta \(incluso si no se registra como una propiedad de dependencia\) debe proporcionar descriptores de acceso get y set estáticos que sigan la convención de nomenclatura `Set`*\[NombreDePropiedadAdjunta\]* y `Get`*\[NombreDePropiedadAdjunta\]*. Se requieren estos descriptores de acceso para que el lector activo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pueda reconocer la propiedad como atributo en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y resolver los tipos adecuados.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## Vea también  
 <xref:System.Windows.DependencyProperty>   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)