---
title: "Cómo: Crear un elemento Grid"
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
helpviewer_keywords: Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30fdd89a46e5d2027e9c525b0ca8cfcfb1d11ed2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-grid-element"></a>Cómo: Crear un elemento Grid
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y usar una instancia de <xref:System.Windows.Controls.Grid> utilizando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código. Este ejemplo usa tres <xref:System.Windows.Controls.ColumnDefinition> objetos y tres <xref:System.Windows.Controls.RowDefinition> objetos crear una cuadrícula que tiene nueve celdas, como se muestra en una hoja de cálculo. Cada celda contiene un <xref:System.Windows.Controls.TextBlock> elemento que representa los datos y la fila superior contiene una <xref:System.Windows.Controls.TextBlock> con el <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad aplicada. Para mostrar los límites de cada celda, el <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propiedad está habilitada.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Grid>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
