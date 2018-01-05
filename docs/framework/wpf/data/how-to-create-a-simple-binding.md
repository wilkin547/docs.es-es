---
title: "Cómo: Crear un enlace sencillo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 108b532e3aea27571c8a3b1290d931e2b0769be9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-simple-binding"></a>Cómo: Crear un enlace sencillo
En este ejemplo se muestra cómo crear un sencillo <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, tiene un `Person` objeto con una propiedad de cadena denominada `PersonName`. El `Person` objeto se define en el espacio de nombres denominado `SDKSample`.  
  
 El ejemplo siguiente crea el `Person` objeto con un `PersonName` el valor de propiedad `Joe`. Esto se hace en el `Resources` sección y asignado un `x:Key`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xaml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 Para enlazar a la `PersonName` propiedad podría hacer lo siguiente:  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Como resultado, el <xref:System.Windows.Controls.TextBlock> aparece con el valor "Joe".  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
