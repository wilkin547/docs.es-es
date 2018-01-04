---
title: "Cómo: Borrar enlaces"
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
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af45d504eb4e7d45808f787925a90c8e0ed19476
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-bindings"></a>Cómo: Borrar enlaces
En este ejemplo se muestra cómo borrar los enlaces de un objeto.  
  
## <a name="example"></a>Ejemplo  
 Para borrar un enlace de una propiedad individual en un objeto, llame a <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> tal como se muestra en el ejemplo siguiente. En el ejemplo siguiente se quita el enlace de la <xref:System.Windows.Controls.TextBlock.TextProperty> de *mytext*, un <xref:System.Windows.Controls.TextBlock> objeto.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Al borrar el enlace, se quita el enlace para que el valor de la propiedad de dependencia cambie al que tendría sin el enlace. Este valor puede ser un valor predeterminado, un valor heredado o un valor de un enlace de la plantilla de datos.  
  
 Para borrar los enlaces de todas las posibles propiedades de un objeto, utilice <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.BindingOperations>  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
