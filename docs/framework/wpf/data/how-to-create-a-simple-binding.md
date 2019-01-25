---
title: Procedimiento Crear un enlace sencillo
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 3e38fa5fd1c7d0a635efd93de6ebe551f1eb1b82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594842"
---
# <a name="how-to-create-a-simple-binding"></a>Procedimiento Crear un enlace sencillo
En este ejemplo se muestra cómo crear una sencilla <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName`. El `Person` objeto está definido en el espacio de nombres denominado `SDKSample`.  
  
 La línea resaltada que contiene el `<src>` crea una instancia de elemento en el ejemplo siguiente la `Person` objeto con un `PersonName` el valor de propiedad `Joe`. Esto se hace en el `Resources` sección y asigna un `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La línea resaltada que contiene el `<TextBlock>` elemento, a continuación, enlaza la <xref:System.Windows.Controls.TextBlock> el control a la `PersonName` propiedad. Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".  
  
## <a name="see-also"></a>Vea también
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
