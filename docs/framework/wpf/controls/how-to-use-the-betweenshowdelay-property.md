---
title: Filtrar Usar la propiedad BetweenShowDelay
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: b6d55c72c8264546949833fc086937a8b1fe2540
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139599"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Filtrar Usar la propiedad BetweenShowDelay
En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad de tiempo para que la información sobre herramientas aparece rápidamente, con poco o ningún retraso, cuando el usuario mueve el puntero del mouse en una información sobre herramientas directamente a otro.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> propiedad está establecida en un segundo (1000 milisegundos) y el <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> se establece en dos segundos (2.000 milisegundos) para la información sobre herramientas de ambos <xref:System.Windows.Shapes.Ellipse> controles. Si se muestra la información sobre herramientas para uno de los puntos suspensivos y, a continuación, mueva el puntero del mouse a otra elipse dentro de dos segundos y pausar en él, la información sobre herramientas de la elipse de la segunda muestra inmediatamente.  
  
 En cualquiera de los siguientes escenarios, el <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> se aplica, lo que hace que la segunda elipse espera un segundo antes de que aparezca la información sobre herramientas:  
  
-   Si el tiempo se tarda en pasar al segundo botón es más de dos segundos.  
  
-   Si la información sobre herramientas no está visible al principio del intervalo de tiempo para la primera elipse.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Temas "Cómo..."](tooltip-how-to-topics.md)
- [Información general de información sobre herramientas](tooltip-overview.md)
