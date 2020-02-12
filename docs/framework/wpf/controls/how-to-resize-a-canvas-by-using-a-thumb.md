---
title: 'Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb'
ms.date: 03/30/2017
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
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124304"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Cómo: Cambiar el tamaño de un lienzo mediante un control Thumb
En este ejemplo se muestra cómo usar un control <xref:System.Windows.Controls.Primitives.Thumb> para cambiar el tamaño de un control <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 El control <xref:System.Windows.Controls.Primitives.Thumb> proporciona funcionalidad de arrastrar que se puede utilizar para desplace o cambiar el tamaño de los controles supervisando los eventos <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> de la <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 El usuario comienza una operación de arrastre presionando el botón primario del mouse cuando el puntero del mouse se pausa en el control de <xref:System.Windows.Controls.Primitives.Thumb>. La operación de arrastrar continúa mientras se presiona el botón primario del mouse. Durante la operación de arrastre, el <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> puede aparecer más de una vez. Cada vez que se produce, la clase <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> proporciona el cambio en la posición correspondiente al cambio en la posición del mouse. Cuando el usuario suelta el botón primario del mouse, finaliza la operación de arrastrar. La operación de arrastre solo proporciona nuevas coordenadas; no cambia automáticamente la posición del <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 En el ejemplo siguiente se muestra un control <xref:System.Windows.Controls.Primitives.Thumb> que es el elemento secundario de un control <xref:System.Windows.Controls.Canvas>. El controlador de eventos para su evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> proporciona la lógica para trasladar el <xref:System.Windows.Controls.Primitives.Thumb> y cambiar el tamaño del <xref:System.Windows.Controls.Canvas>. Los controladores de eventos para el evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> cambian el color de la <xref:System.Windows.Controls.Primitives.Thumb> durante una operación de arrastre. En el ejemplo siguiente se define el <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> que mueve el <xref:System.Windows.Controls.Primitives.Thumb> y cambia el tamaño del <xref:System.Windows.Controls.Canvas> en respuesta a un movimiento del mouse.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Para obtener el ejemplo completo, vea [ejemplo de funcionalidad de arrastre Thumb](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
