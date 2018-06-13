---
title: 'Cómo: Invalidar el método OnRender de un objeto Panel'
ms.date: 03/30/2017
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
ms.openlocfilehash: e591bc195d3b0ba58002bda42ddb3e9ed35d312e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554877"
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
