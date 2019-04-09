---
title: Filtrar Invalidar metadatos en una propiedad de dependencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
ms.openlocfilehash: 7f20708722660aa4f86462efd50939935f840613
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209442"
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a>Filtrar Invalidar metadatos en una propiedad de dependencia
En este ejemplo se muestra cómo invalidar los metadatos de propiedad de dependencia predeterminados que procede de una clase heredada, mediante una llamada a la <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> método y proporcionar metadatos específicos del tipo.  
  
## <a name="example"></a>Ejemplo  
 Al definir su <xref:System.Windows.PropertyMetadata>, una clase puede definir los comportamientos de la propiedad de dependencia, como sus valor predeterminado valor y propiedad del sistema las devoluciones de llamada. Muchas clases de propiedad de dependencia ya tienen metadatos predeterminados establecidos como parte de su proceso de registro. Esto incluye las propiedades de dependencia que forman parte de la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Una clase que hereda la propiedad de dependencia a través de la herencia de clase puede invalidar los metadatos originales para que las características de la propiedad que se pueden modificar mediante metadatos coincidan con los requisitos específicos de la subclase.  
  
 La invalidación de metadatos en una propiedad de dependencia debe realizarse antes de que el sistema de propiedades ponga la propiedad en uso (esto equivale al momento en el que se crean instancias de objetos que registran la propiedad). Las llamadas a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> debe realizarse dentro de los constructores estáticos del tipo que se proporciona como el `forType` parámetro de <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Si intenta cambiar los metadatos cuando ya existan instancias del tipo de propietario, no producirá excepciones, pero generará comportamientos incoherentes en el sistema de propiedades. Además, los metadatos solo se pueden invalidar una vez por tipo. Los intentos posteriores de invalidar metadatos en el mismo tipo generarán una excepción.  
  
 En el ejemplo siguiente, la clase personalizada `MyAdvancedStateControl` invalida los metadatos proporcionados para `StateProperty` por `MyAdvancedStateControl` con nuevos metadatos de propiedad. Por ejemplo, el valor predeterminado de `StateProperty` es ahora `true` cuando se consulta la propiedad en una instancia `MyAdvancedStateControl` de construcción reciente.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty>
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Temas "Cómo..."](properties-how-to-topics.md)
