---
title: 'Cómo: Implementar una propiedad de dependencia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: b0c5b33d841f43249f9559bd31f1ef8fe66ff05e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544653"
---
# <a name="how-to-implement-a-dependency-property"></a>Cómo: Implementar una propiedad de dependencia
Este ejemplo muestra cómo realizar copias de un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] propiedad con un <xref:System.Windows.DependencyProperty> campo, lo que define una propiedad de dependencia. Si define sus propias propiedades y quiere que admitan muchos aspectos de la funcionalidad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], incluidos los estilos, el enlace de datos, la herencia, la animación y los valores predeterminados, debe implementarlas como una propiedad de dependencia.  
  
## <a name="example"></a>Ejemplo  
 En primer lugar, el ejemplo siguiente registra una propiedad de dependencia mediante una llamada a la <xref:System.Windows.DependencyProperty.Register%2A> método. El nombre del campo de identificador que se utiliza para almacenar el nombre y las características de la propiedad de dependencia deben ser el <xref:System.Windows.DependencyProperty.Name%2A> que eligió para la propiedad de dependencia como parte de la <xref:System.Windows.DependencyProperty.Register%2A> llamada, seguido de la cadena literal `Property`. Por ejemplo, si registra una propiedad de dependencia con un <xref:System.Windows.DependencyProperty.Name%2A> de `Location`, a continuación, el campo de identificador que se define para la propiedad de dependencia debe denominarse `LocationProperty`.  
  
 En este ejemplo, el nombre de la propiedad de dependencia y su [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] descriptor de acceso es `State`; el campo de identificador es `StateProperty`; el tipo de la propiedad es <xref:System.Boolean>; y el tipo que se registra la propiedad de dependencia es `MyStateControl`.  
  
 Si no sigue este patrón de nomenclatura, es posible que los diseñadores no puedan notificar la propiedad correctamente y que ciertos aspectos de la aplicación de estilos del sistema de propiedades no funcionen según lo previsto.  
  
 También puede especificar los metadatos predeterminados de una propiedad de dependencia. En este ejemplo se registra el valor predeterminado de la propiedad de dependencia `State` para que sea `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Para obtener más información acerca de cómo y por qué se debe implementar una propiedad de dependencia, en lugar de respaldar simplemente una propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con un campo privado, consulte [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
