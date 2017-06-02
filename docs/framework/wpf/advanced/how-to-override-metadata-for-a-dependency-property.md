---
title: "C&#243;mo: Invalidar metadatos en una propiedad de dependencia | Microsoft Docs"
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
  - "propiedades de dependencia, invalidar metadatos para"
  - "metadatos, invalidar para propiedades de dependencia"
  - "invalidar metadatos para propiedades de dependencia"
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Invalidar metadatos en una propiedad de dependencia
En este ejemplo se muestra cómo invalidar los metadatos de propiedad de dependencia predeterminados que proceden de una clase heredada, llamando al método <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> y proporcionando metadatos específicos del tipo.  
  
## Ejemplo  
 Mediante la definición de <xref:System.Windows.PropertyMetadata>, una clase puede definir los comportamientos de una [propiedad de dependencia](GTMT), tales como su valor predeterminado las y devoluciones de llamada del sistema de propiedades.  Muchas clases de propiedades de dependencia ya tienen metadatos predeterminados establecidos como parte de su proceso de registro.  Esto incluye las propiedades de dependencia que forman parte de las [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Una clase que hereda la propiedad de dependencia a través de su herencia de clases puede invalidar los metadatos originales de tal forma que las características de la propiedad que se pueden modificar mediante metadatos coincidan con los requisitos específicos de la subclase.  
  
 La invalidación de metadatos en una propiedad de dependencia se debe hacer antes de colocar esa propiedad para su uso por el sistema de propiedades \(esto equivale al momento en que se crean instancias específicas de los objetos que registran la propiedad\).  Las llamadas a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> se deben realizar dentro de los constructores estáticos del tipo que se proporciona como parámetro `forType` de <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.  Si se intentan cambiar los metadatos después de que existan instancias de tipo de propietario, no se iniciarán excepciones, pero se provocarán comportamientos incoherentes en el sistema de propiedades.  Asimismo, los metadatos sólo se pueden invalidar una vez para cada tipo.  Cualquier intento subsiguiente de invalidar los metadatos en el mismo tipo iniciará una excepción.  
  
 En el ejemplo siguiente, la clase `MyAdvancedStateControl` personalizada invalida los metadatos proporcionados para `StateProperty` mediante `MyAdvancedStateControl` con nuevos metadatos de propiedad.  Ahora, por ejemplo, el valor predeterminado de `StateProperty` es `true` cuando se consulta la propiedad en una instancia de `MyAdvancedStateControl` recién construida.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## Vea también  
 <xref:System.Windows.DependencyProperty>   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)