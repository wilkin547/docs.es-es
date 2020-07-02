---
title: 'Cómo: Crear un enlace sencillo'
description: Cree un enlace simple para las aplicaciones mediante este ejemplo de procedimientos en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618706"
---
# <a name="how-to-create-a-simple-binding"></a>Cómo: Crear un enlace sencillo
En este ejemplo se muestra cómo crear un sencillo <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName` . El `Person` objeto se define en el espacio de nombres denominado `SDKSample` .  
  
 La línea resaltada que contiene el `<src>` elemento en el ejemplo siguiente crea una instancia del `Person` objeto con un `PersonName` valor de propiedad de `Joe` . Esto se hace en la `Resources` sección y se le asigna un `x:Key` .  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La línea resaltada que contiene el `<TextBlock>` elemento enlaza el <xref:System.Windows.Controls.TextBlock> control a la `PersonName` propiedad. Como resultado, <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
