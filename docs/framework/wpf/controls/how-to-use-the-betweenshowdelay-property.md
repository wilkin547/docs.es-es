---
title: 'Cómo: Usar la propiedad BetweenShowDelay'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 7d48fb859ec6d37abd2490bc718d58cbdaa67f13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552719"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Cómo: Usar la propiedad BetweenShowDelay
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad de tiempo para que la información sobre herramientas aparezca rápidamente, con poco o ningún retraso: cuando un usuario mueve el puntero del mouse en una información sobre herramientas directamente a otro.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> propiedad se establece en un segundo (1000 milisegundos) y la <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> se establece en dos segundos (2000 milisegundos) para la información sobre herramientas de ambos <xref:System.Windows.Shapes.Ellipse> controles. Si mostrar la información sobre herramientas para uno de los puntos suspensivos y, a continuación, mueva el puntero del mouse a otra elipse dentro de dos segundos y pausa en él, la información sobre herramientas de la segunda elipse se muestra inmediatamente.  
  
 En cualquiera de los siguientes escenarios, el <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> se aplica, lo que hace que la segunda elipse espera un segundo antes de que aparezca la información sobre herramientas:  
  
-   Si el tiempo necesario para mover al segundo botón es superior a dos segundos.  
  
-   Si la información sobre herramientas no está visible al principio del intervalo de tiempo para la primera elipse.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [Información general de información sobre herramientas](../../../../docs/framework/wpf/controls/tooltip-overview.md)
