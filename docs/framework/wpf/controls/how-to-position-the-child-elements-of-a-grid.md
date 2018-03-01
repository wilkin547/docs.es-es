---
title: "Cómo: Situar los elementos secundarios de un control Grid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Cómo: Situar los elementos secundarios de un control Grid
Este ejemplo muestra cómo utilizar get y establecer métodos que se definen en <xref:System.Windows.Controls.Grid> para colocar los elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un elemento primario <xref:System.Windows.Controls.Grid> elemento (`grid1`) que tiene tres columnas y tres filas. Un elemento secundario <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) se agrega a la <xref:System.Windows.Controls.Grid> en posición cero de la columna, posición cero de la fila. <xref:System.Windows.Controls.Button>los elementos representan los métodos que se pueden llamar para volver a colocar el <xref:System.Windows.Shapes.Rectangle> elemento dentro de la <xref:System.Windows.Controls.Grid>. Cuando un usuario hace clic en un botón, se activa el método relacionado.  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 En el siguiente ejemplo de código subyacente controla los métodos que el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generar eventos. El ejemplo escribe estas llamadas a métodos <xref:System.Windows.Controls.TextBlock> elementos que use relacionado métodos get para generar los nuevos valores de propiedad como cadenas.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Grid>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
