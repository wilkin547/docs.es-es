---
title: "C&#243;mo: Agregar un tipo de propietario para una propiedad de dependencia | Microsoft Docs"
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
  - "clases, agregar como propietarias de propiedades de dependencia"
  - "propiedades de dependencia, agregar clases como propietarias de"
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Agregar un tipo de propietario para una propiedad de dependencia
En este ejemplo se muestra cómo agregar una clase como un propietario de una propiedad de dependencia registrada para un tipo diferente.  Al hacerlo, el lector y el sistema de propiedades de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden reconocer la clase como un propietario adicional de la propiedad.  Al realizar la adición como propietario, la clase de adición puede proporcionar metadatos específicos del tipo.  
  
 En el ejemplo siguiente, `StateProperty` es una propiedad registrada por la clase `MyStateControl`.  La clase `UnrelatedStateControl` se agrega como un propietario de `StateProperty` mediante el método <xref:System.Windows.DependencyProperty.AddOwner%2A>, utilizando en concreto la firma que permite utilizar nuevos metadatos para la propiedad de dependencia que existen en el tipo de adición.  Observe que debe proporcionar descriptores de acceso [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] para la propiedad de modo similar al ejemplo mostrado en [Implementar una propiedad de dependencia](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md), así como volver a exponer el identificador de la propiedad de dependencia en la clase que se agrega como propietario.  
  
 Sin contenedores, la propiedad de dependencia seguiría funcionando desde la perspectiva de acceso mediante programación utilizando <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>.  Sin embargo, suele ser conveniente imitar este comportamiento del sistema de propiedades mediante los contenedores de propiedades [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Los contenedores facilitan el establecimiento de la propiedad de dependencia mediante programación y permiten establecer las propiedades como atributos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Para averiguar cómo invalidar los metadatos predeterminados, vea [Invalidar metadatos en una propiedad de dependencia](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## Ejemplo  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## Vea también  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)