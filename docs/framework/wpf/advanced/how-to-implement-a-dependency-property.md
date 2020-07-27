---
title: 'Cómo: Implementar una propiedad de dependencia'
description: Defina una propiedad de dependencia en Windows Presentation Foundation, mediante la copia de seguridad de una propiedad de Common Language Runtime con un campo DependencyProperty.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165098"
---
# <a name="how-to-implement-a-dependency-property"></a>Cómo: Implementar una propiedad de dependencia
En este ejemplo se muestra cómo hacer una copia de seguridad de una propiedad de Common Language Runtime (CLR) con un <xref:System.Windows.DependencyProperty> campo, con lo que se define una propiedad de dependencia. Si define sus propias propiedades y quiere que admitan muchos aspectos de la funcionalidad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], incluidos los estilos, el enlace de datos, la herencia, la animación y los valores predeterminados, debe implementarlas como una propiedad de dependencia.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, primero se registra una propiedad de dependencia mediante una llamada al <xref:System.Windows.DependencyProperty.Register%2A> método. El nombre del campo de identificador que se usa para almacenar el nombre y las características de la propiedad de dependencia debe ser el <xref:System.Windows.DependencyProperty.Name%2A> elegido para la propiedad de dependencia como parte de la <xref:System.Windows.DependencyProperty.Register%2A> llamada, anexado por la cadena literal `Property` . Por ejemplo, si registra una propiedad de dependencia con un <xref:System.Windows.DependencyProperty.Name%2A> de `Location` , el campo de identificador que defina para la propiedad de dependencia debe denominarse `LocationProperty` .  
  
 En este ejemplo, el nombre de la propiedad de dependencia y su descriptor de acceso CLR es `State` ; el campo de identificador es `StateProperty` ; el tipo de la propiedad es <xref:System.Boolean> ; y el tipo que registra la propiedad de dependencia es `MyStateControl` .  
  
 Si no sigue este patrón de nomenclatura, es posible que los diseñadores no puedan notificar la propiedad correctamente y que ciertos aspectos de la aplicación de estilos del sistema de propiedades no funcionen según lo previsto.  
  
 También puede especificar los metadatos predeterminados de una propiedad de dependencia. En este ejemplo se registra el valor predeterminado de la propiedad de dependencia `State` para que sea `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Para obtener más información sobre cómo y por qué implementar una propiedad de dependencia, en lugar de hacer una copia de seguridad de una propiedad de CLR con un campo privado, vea [información general sobre las propiedades de dependencia](dependency-properties-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Temas "Cómo..."](properties-how-to-topics.md)
