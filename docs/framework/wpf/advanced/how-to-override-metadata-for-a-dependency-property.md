---
title: "Cómo: Invalidar metadatos en una propiedad de dependencia"
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
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e7cb01c81b5fb24830cbe0cc39befbadaf4405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a>Cómo: Invalidar metadatos en una propiedad de dependencia
Este ejemplo muestra cómo invalidar los metadatos de propiedad de dependencia predeterminados que proceden de una clase heredada, mediante una llamada a la <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> método y proporcionar metadatos específicos del tipo.  
  
## <a name="example"></a>Ejemplo  
 Mediante la definición de su <xref:System.Windows.PropertyMetadata>, una clase puede definir los comportamientos de la propiedad de dependencia, como sus valor predeterminado propiedad y valor sistema las devoluciones de llamada. Muchas clases de propiedad de dependencia ya tienen metadatos predeterminados establecidos como parte de su proceso de registro. Esto incluye las propiedades de dependencia que forman parte de la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Una clase que hereda la propiedad de dependencia a través de la herencia de clase puede invalidar los metadatos originales para que las características de la propiedad que se pueden modificar mediante metadatos coincidan con los requisitos específicos de la subclase.  
  
 La invalidación de metadatos en una propiedad de dependencia debe realizarse antes de que el sistema de propiedades ponga la propiedad en uso (esto equivale al momento en el que se crean instancias de objetos que registran la propiedad). Las llamadas a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> debe realizarse dentro de los constructores estáticos del tipo que se proporciona como el `forType` parámetro de <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Si intenta cambiar los metadatos cuando ya existan instancias del tipo de propietario, no producirá excepciones, pero generará comportamientos incoherentes en el sistema de propiedades. Además, los metadatos solo se pueden invalidar una vez por tipo. Los intentos posteriores de invalidar metadatos en el mismo tipo generarán una excepción.  
  
 En el ejemplo siguiente, la clase personalizada `MyAdvancedStateControl` invalida los metadatos proporcionados para `StateProperty` por `MyAdvancedStateControl` con nuevos metadatos de propiedad. Por ejemplo, el valor predeterminado de `StateProperty` es ahora `true` cuando se consulta la propiedad en una instancia `MyAdvancedStateControl` de construcción reciente.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.DependencyProperty>  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
