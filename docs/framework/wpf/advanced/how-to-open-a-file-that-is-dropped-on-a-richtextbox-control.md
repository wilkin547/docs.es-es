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
ms.openlocfilehash: 408d48856362fa8a77a44e2cc97cb2d5ff608dcf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046350"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Procedimiento Abrir un archivo colocado en un control RichTextBox

En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], los <xref:System.Windows.Controls.TextBox>controles <xref:System.Windows.Controls.RichTextBox>, y<xref:System.Windows.Documents.FlowDocument> tienen la funcionalidad integrada de arrastrar y colocar. La funcionalidad integrada permite arrastrar y colocar texto dentro de los controles y entre ellos. Sin embargo, no permite abrir un archivo colocando el archivo en el control. Estos controles también marcan los eventos de arrastrar y colocar como controlados. Como resultado, de forma predeterminada, no se pueden agregar controladores de eventos propios para proporcionar la funcionalidad para abrir archivos colocados.

Para agregar un control adicional para los eventos de arrastrar y colocar en estos controles, use <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> el método para agregar los controladores de eventos para los eventos de arrastrar y colocar. Establezca el `handledEventsToo` parámetro en `true` para que se invoque el controlador especificado para un evento enrutado que ya esté marcado como controlado por otro elemento a lo largo de la ruta del evento.

> [!TIP]
> Puede reemplazar la funcionalidad integrada de arrastrar y colocar de <xref:System.Windows.Controls.TextBox>, y <xref:System.Windows.Documents.FlowDocument> controlando las <xref:System.Windows.Controls.RichTextBox>versiones preliminares de los eventos de arrastrar y colocar, y marcando los eventos de vista previa como controlados. Sin embargo, esto deshabilitará la funcionalidad integrada de arrastrar y colocar, y no se recomienda.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo agregar controladores para los <xref:System.Windows.DragDrop.DragOver> eventos <xref:System.Windows.DragDrop.Drop> y en <xref:System.Windows.Controls.RichTextBox>. En este ejemplo se <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> usa el método y `handledEventsToo` se establece `true` el parámetro en para que se invoquen los controladores de eventos <xref:System.Windows.Controls.RichTextBox> aunque el control Marque estos eventos como controlados. El código de los controladores de eventos agrega funcionalidad para abrir un archivo de texto que se coloca en <xref:System.Windows.Controls.RichTextBox>.

Para probar este ejemplo, arrastre un archivo de texto o un archivo de formato de texto enriquecido (RTF) desde el <xref:System.Windows.Controls.RichTextBox>explorador de Windows hasta el. El archivo se abrirá en el <xref:System.Windows.Controls.RichTextBox>. Si presiona la tecla Mayús antes de colocar el archivo, el archivo se abrirá como texto sin formato.

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
