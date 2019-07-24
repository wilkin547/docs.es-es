---
title: Procedimiento Implementar una propiedad de dependencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 6f2fb9b0824feb6253527de063f58da2427d0c06
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400357"
---
# <a name="how-to-implement-a-dependency-property"></a>Procedimiento Implementar una propiedad de dependencia
En este ejemplo se muestra cómo hacer una copia de seguridad de una propiedad <xref:System.Windows.DependencyProperty> de Common Language Runtime (CLR) con un campo, con lo que se define una propiedad de dependencia. Si define sus propias propiedades y quiere que admitan muchos aspectos de la funcionalidad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], incluidos los estilos, el enlace de datos, la herencia, la animación y los valores predeterminados, debe implementarlas como una propiedad de dependencia.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, primero se registra una propiedad de dependencia <xref:System.Windows.DependencyProperty.Register%2A> mediante una llamada al método. El nombre del campo de identificador que se usa para almacenar el nombre y las características de la propiedad de dependencia debe ser <xref:System.Windows.DependencyProperty.Name%2A> el elegido para la propiedad de dependencia como parte de <xref:System.Windows.DependencyProperty.Register%2A> la llamada, anexado por la cadena `Property`literal. Por ejemplo, si registra una propiedad de dependencia con un <xref:System.Windows.DependencyProperty.Name%2A> de `Location`, el campo de identificador que defina para la propiedad de dependencia debe denominarse `LocationProperty`.  
  
 En este ejemplo, el nombre de la propiedad de dependencia y su descriptor `State`de acceso CLR es; el campo de identificador es `StateProperty`; el <xref:System.Boolean>tipo de la propiedad es; y el tipo que registra `MyStateControl`la propiedad de dependencia es.  
  
 Si no sigue este patrón de nomenclatura, es posible que los diseñadores no puedan notificar la propiedad correctamente y que ciertos aspectos de la aplicación de estilos del sistema de propiedades no funcionen según lo previsto.  
  
 También puede especificar los metadatos predeterminados de una propiedad de dependencia. En este ejemplo se registra el valor predeterminado de la propiedad de dependencia `State` para que sea `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Para obtener más información sobre cómo y por qué implementar una propiedad de dependencia, en lugar de hacer una copia de seguridad de una propiedad de CLR con un campo privado, vea [información general sobre las propiedades de dependencia](dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Temas "Cómo..."](properties-how-to-topics.md)
