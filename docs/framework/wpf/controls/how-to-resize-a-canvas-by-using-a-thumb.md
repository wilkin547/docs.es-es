---
title: "Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb"
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
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 757745b24c8e9e281d243cd15a5351b01d3479ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Controls.Primitives.Thumb> control para cambiar el tamaño de una <xref:System.Windows.Controls.Canvas> control.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.Primitives.Thumb> control proporciona la funcionalidad de arrastrar que se puede utilizar para mover o cambiar el tamaño de los controles mediante la supervisión de la <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventos de la <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 El usuario comienza una operación de arrastre presionando el botón primario del mouse cuando se pausa el puntero del mouse en el <xref:System.Windows.Controls.Primitives.Thumb> control. La operación de arrastrar continúa mientras mantiene presionado el botón primario del mouse. Durante la operación de arrastre, el <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> puede aparecer más de una vez. Cada vez que aparezca, la <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> clase proporciona el cambio de posición que se corresponde con el cambio en la posición del mouse. Cuando el usuario suelta el botón primario del mouse, finaliza la operación de arrastre. La operación de arrastrar sólo proporciona coordenadas nuevas; No volver a colocar automáticamente la <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 El ejemplo siguiente muestra un <xref:System.Windows.Controls.Primitives.Thumb> control que es el elemento secundario de un <xref:System.Windows.Controls.Canvas> control. El controlador de eventos para su <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento proporciona la lógica para mover el <xref:System.Windows.Controls.Primitives.Thumb> y cambiar el tamaño de la <xref:System.Windows.Controls.Canvas>. Los controladores de eventos para el <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> evento cambiar el color de la <xref:System.Windows.Controls.Primitives.Thumb> durante una operación de arrastre. En el ejemplo siguiente se define la <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 El siguiente ejemplo se muestra la <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> controlador de eventos que se mueve el <xref:System.Windows.Controls.Primitives.Thumb> y cambia el tamaño de la <xref:System.Windows.Controls.Canvas> en respuesta a un movimiento del mouse.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 El siguiente ejemplo se muestra la <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> controlador de eventos.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 El siguiente ejemplo se muestra la <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> controlador de eventos.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Para obtener un ejemplo completo, vea [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
