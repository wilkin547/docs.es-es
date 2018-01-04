---
title: "Cómo: Invalidar el método OnRender de un objeto Panel"
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
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 958595cdfa521b372270d6283c7134ef0ba0ef79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a>Cómo: Invalidar el método OnRender de un objeto Panel
Este ejemplo muestra cómo invalidar el <xref:System.Windows.Controls.Panel.OnRender%2A> método <xref:System.Windows.Controls.Panel> para agregar efectos gráficos personalizados a un elemento de diseño.  
  
## <a name="example"></a>Ejemplo  
 Use la <xref:System.Windows.Controls.Panel.OnRender%2A> método para agregar efectos gráficos a un elemento del panel representado. Por ejemplo, puede usar este método para agregar un borde personalizado o efectos de fondo. Un <xref:System.Windows.Media.DrawingContext> objeto se pasa como argumento, que proporciona métodos para dibujar formas, texto, imágenes o vídeos. Como resultado, este método es útil para la personalización de un objeto de panel.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Panel>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Ejemplo Custom Radial Panel](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
