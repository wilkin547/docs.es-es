---
title: "C&#243;mo: Cambiar el tama&#241;o de un lienzo mediante un control Thumb | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Canvas (control)"
  - "controles, Canvas"
  - "controles, Thumb"
  - "cambiar el tamaño del control Canvas"
  - "Thumb (control)"
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Cambiar el tama&#241;o de un lienzo mediante un control Thumb
En este ejemplo se muestra cómo usar un control <xref:System.Windows.Controls.Primitives.Thumb> para cambiar el tamaño de un control <xref:System.Windows.Controls.Canvas>.  
  
## Ejemplo  
 El control <xref:System.Windows.Controls.Primitives.Thumb> proporciona funcionalidad de arrastrar que se puede usar para mover o cambiar de tamaño los controles al supervisar los eventos <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> de <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 El usuario comienza una operación de arrastrar al presionar el botón primario del mouse cuando el puntero se pausa en el control <xref:System.Windows.Controls.Primitives.Thumb>.  La operación de arrastrar continúa mientras el botón primario se mantiene presionado.  Durante la operación de arrastrar, puede producirse el evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> más de una vez.  Cada vez que se produce, la clase <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> proporciona el cambio de posición que corresponde al cambio de la posición del mouse.  Cuando el usuario suelta el botón primario del mouse, la operación de arrastrar finaliza.  La operación de arrastrar sólo proporciona coordenadas nuevas; no cambia la posición de <xref:System.Windows.Controls.Primitives.Thumb> automáticamente.  
  
 En el ejemplo siguiente se muestra un control <xref:System.Windows.Controls.Primitives.Thumb> que es el elemento secundario de un control <xref:System.Windows.Controls.Canvas>.  El controlador de evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> proporciona lógica para mover <xref:System.Windows.Controls.Primitives.Thumb> y cambiar el tamaño de <xref:System.Windows.Controls.Canvas>.  Los controladores de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> y <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> cambian el color de <xref:System.Windows.Controls.Primitives.Thumb> durante una operación de arrastrar.  En el ejemplo siguiente se define <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 En el ejemplo siguiente se muestra el controlador de evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> que mueve <xref:System.Windows.Controls.Primitives.Thumb> y cambia el tamaño de <xref:System.Windows.Controls.Canvas> como respuesta a un movimiento del mouse.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 En el ejemplo siguiente se muestra el controlador de evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 En el ejemplo siguiente se muestra el controlador de eventos <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Para obtener el ejemplo completo, vea [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## Vea también  
 <xref:System.Windows.Controls.Primitives.Thumb>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>