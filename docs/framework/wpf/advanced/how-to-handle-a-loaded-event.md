---
title: "Cómo: Controlar un evento cargado"
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
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 794de0e64e2f4d974091b92f211d7472d04ecd26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-a-loaded-event"></a>Cómo: Controlar un evento cargado
Este ejemplo muestra cómo controlar la <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> eventos y un escenario adecuado para controlar ese evento. El controlador crea una <xref:System.Windows.Controls.Button> cuando se carga la página.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] junto con un archivo de código subyacente.  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement>  
 [Eventos de duración de objetos](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
