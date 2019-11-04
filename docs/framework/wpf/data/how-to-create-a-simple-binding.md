---
title: 'Cómo: Crear un enlace sencillo'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453502"
---
# <a name="how-to-create-a-simple-binding"></a>Cómo: Crear un enlace sencillo
En este ejemplo se muestra cómo crear un <xref:System.Windows.Data.Binding>simple.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, tiene un objeto de `Person` con una propiedad de cadena denominada `PersonName`. El objeto de `Person` se define en el espacio de nombres denominado `SDKSample`.  
  
 La línea resaltada que contiene el elemento `<src>` en el ejemplo siguiente crea una instancia del objeto `Person` con un valor de propiedad `PersonName` de `Joe`. Esto se hace en la sección `Resources` y se le asigna un `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La línea resaltada que contiene el elemento `<TextBlock>` enlaza el control de <xref:System.Windows.Controls.TextBlock> a la propiedad `PersonName`. Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
