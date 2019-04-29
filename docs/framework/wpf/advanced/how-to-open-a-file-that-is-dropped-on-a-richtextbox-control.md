---
title: Procedimiento Abrir un archivo colocado en un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 8ffa4c9919788060dc4524e127c181ee8282e6f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768607"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Procedimiento Abrir un archivo colocado en un control RichTextBox
En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Documents.FlowDocument> todos los controles tienen funcionalidad integrada de arrastrar y colocar. La funcionalidad integrada permite arrastrar y colocar texto dentro y entre los controles. Sin embargo, no permite abrir un archivo colocando el archivo en el control. Estos controles también marcan los eventos de arrastrar y colocar como controlado. Como resultado, de forma predeterminada, no se puede agregar sus propios controladores de eventos para proporcionar la funcionalidad para abrir los archivos colocados.  
  
 Para agregar un control adicional para los eventos de arrastrar y colocar en estos controles, use el <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> método para agregar los controladores de eventos para los eventos de arrastrar y colocar. Establecer el `handledEventsToo` parámetro `true` para que el controlador especificado se invoque para un evento enrutado que ya se ha marcado como controlado por otro elemento a lo largo de la ruta del evento.  
  
> [!TIP]
>  Puede reemplazar la funcionalidad de arrastrar y colocar integrada de <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Documents.FlowDocument> controlando las versiones preliminares de los eventos de arrastrar y colocar y marcar los eventos de vista previa como controlados. Sin embargo, Esto deshabilitará la funcionalidad integrada de arrastrar y colocar y no se recomienda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar controladores para la <xref:System.Windows.DragDrop.DragOver> y <xref:System.Windows.DragDrop.Drop> eventos en un <xref:System.Windows.Controls.RichTextBox>. Este ejemplo se usa el <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> método y los conjuntos de la `handledEventsToo` parámetro `true` para que se va a invocar, aunque los controladores de eventos el <xref:System.Windows.Controls.RichTextBox> marca estos eventos como controlados. El código en los controladores de eventos agrega funcionalidad para abrir un archivo de texto que se ha quitado en el <xref:System.Windows.Controls.RichTextBox>.  
  
 Para probar este ejemplo, arrastre un archivo de texto o un archivo de texto enriquecido (RTF) formato desde el Explorador de Windows para el <xref:System.Windows.Controls.RichTextBox>. Se abrirá el archivo en el <xref:System.Windows.Controls.RichTextBox>. Si presiona la tecla MAYÚS antes de quitar el archivo, se abrirá el archivo como texto sin formato.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
