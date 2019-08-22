---
title: Filtrar Invalidar el método OnRender de un objeto Panel
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
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666713"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Filtrar Invalidar el método OnRender de un objeto Panel
En este ejemplo se muestra cómo invalidar <xref:System.Windows.Controls.Panel.OnRender%2A> el <xref:System.Windows.Controls.Panel> método de para agregar efectos gráficos personalizados a un elemento de diseño.  
  
## <a name="example"></a>Ejemplo  
 Use el <xref:System.Windows.Controls.Panel.OnRender%2A> método para agregar efectos gráficos a un elemento del panel representado. Por ejemplo, puede utilizar este método para agregar efectos de borde o de fondo personalizados. Un <xref:System.Windows.Media.DrawingContext> objeto se pasa como argumento, que proporciona métodos para dibujar formas, texto, imágenes o vídeos. Como resultado, este método es útil para la personalización de un objeto de panel.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Panel>
- [Información general sobre elementos Panel](panels-overview.md)
- [Temas "Cómo..."](panel-how-to-topics.md)
