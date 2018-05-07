---
title: 'Cómo: Abrir un archivo colocado en un control RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: f3c10ae76a9afcc04578c590cc57cd43c3ab7a1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Cómo: Abrir un archivo colocado en un control RichTextBox
En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Documents.FlowDocument> todos los controles tienen funcionalidad de arrastrar y colocar integrada. La funcionalidad integrada permite arrastrar y colocar dentro y entre los controles de texto. Sin embargo, no permite abrir un archivo si se coloca el archivo en el control. Estos controles también marcan los eventos de arrastrar y colocar como controlado. Como resultado, de forma predeterminada, no se puede agregar sus propios controladores de eventos para proporcionar la funcionalidad para abrir archivos colocados.  
  
 Para agregar un control adicional para eventos de arrastrar y colocar en estos controles, use el <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> método para agregar los controladores de eventos para los eventos de arrastrar y colocar. Establecer el `handledEventsToo` parámetro `true` para que el controlador especificado se invoque para un evento enrutado que ya se ha marcado como controlado por otro elemento a lo largo de la ruta del evento.  
  
> [!TIP]
>  Puede reemplazar la funcionalidad de arrastrar y colocar integrada de <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Documents.FlowDocument> controlando las versiones de vista previa de los eventos de arrastrar y colocar y marcar los eventos de vista previa como controlado. Sin embargo, Esto deshabilitará la funcionalidad de arrastrar y colocar integrada y no se recomienda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar controladores para la <xref:System.Windows.DragDrop.DragOver> y <xref:System.Windows.DragDrop.Drop> eventos en un <xref:System.Windows.Controls.RichTextBox>. Este ejemplo se utiliza la <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> método y establece el `handledEventsToo` parámetro para `true` para que los controladores de eventos se invocará aunque el <xref:System.Windows.Controls.RichTextBox> marca estos eventos como controlado. El código en los controladores de eventos agrega funcionalidad para abrir un archivo de texto que se coloca en el <xref:System.Windows.Controls.RichTextBox>.  
  
 Para probar este ejemplo, arrastre un archivo de texto o un archivo de texto enriquecido (RTF) formato desde el Explorador de Windows para el <xref:System.Windows.Controls.RichTextBox>. El archivo se abrirá en el <xref:System.Windows.Controls.RichTextBox>. Si presiona la tecla MAYÚS antes de la eliminación del archivo, se abrirá el archivo como texto sin formato.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
