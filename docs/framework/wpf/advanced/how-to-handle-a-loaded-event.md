---
title: Filtrar Controlar un evento cargado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: b8cd2f5e9d848cebb712e7b4930ca39efe48ecc0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122556"
---
# <a name="how-to-handle-a-loaded-event"></a>Filtrar Controlar un evento cargado
En este ejemplo se muestra cómo controlar el <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> eventos y un escenario adecuado para controlar ese evento. El controlador crea un <xref:System.Windows.Controls.Button> cuando se cargue la página.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] junto con un archivo de código subyacente.  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement>
- [Eventos de duración de objetos](object-lifetime-events.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](base-elements-how-to-topics.md)
