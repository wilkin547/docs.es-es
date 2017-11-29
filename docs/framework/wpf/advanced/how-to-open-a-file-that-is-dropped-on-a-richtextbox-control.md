---
title: "Cómo: Abrir un archivo colocado en un control RichTextBox"
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
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f65ecaf9c6ef34176967e1ebf9134ceee195036b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="fccef-102">Cómo: Abrir un archivo colocado en un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fccef-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="fccef-103">En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Documents.FlowDocument> todos los controles tienen funcionalidad de arrastrar y colocar integrada.</span><span class="sxs-lookup"><span data-stu-id="fccef-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="fccef-104">La funcionalidad integrada permite arrastrar y colocar dentro y entre los controles de texto.</span><span class="sxs-lookup"><span data-stu-id="fccef-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="fccef-105">Sin embargo, no permite abrir un archivo si se coloca el archivo en el control.</span><span class="sxs-lookup"><span data-stu-id="fccef-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="fccef-106">Estos controles también marcan los eventos de arrastrar y colocar como controlado.</span><span class="sxs-lookup"><span data-stu-id="fccef-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="fccef-107">Como resultado, de forma predeterminada, no se puede agregar sus propios controladores de eventos para proporcionar la funcionalidad para abrir archivos colocados.</span><span class="sxs-lookup"><span data-stu-id="fccef-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="fccef-108">Para agregar un control adicional para eventos de arrastrar y colocar en estos controles, use el <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> método para agregar los controladores de eventos para los eventos de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="fccef-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="fccef-109">Establecer el `handledEventsToo` parámetro `true` para que el controlador especificado se invoque para un evento enrutado que ya se ha marcado como controlado por otro elemento a lo largo de la ruta del evento.</span><span class="sxs-lookup"><span data-stu-id="fccef-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="fccef-110">Puede reemplazar la funcionalidad de arrastrar y colocar integrada de <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Documents.FlowDocument> controlando las versiones de vista previa de los eventos de arrastrar y colocar y marcar los eventos de vista previa como controlado.</span><span class="sxs-lookup"><span data-stu-id="fccef-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="fccef-111">Sin embargo, Esto deshabilitará la funcionalidad de arrastrar y colocar integrada y no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="fccef-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fccef-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fccef-112">Example</span></span>  
 <span data-ttu-id="fccef-113">En el ejemplo siguiente se muestra cómo agregar controladores para la <xref:System.Windows.DragDrop.DragOver> y <xref:System.Windows.DragDrop.Drop> eventos en un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="fccef-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="fccef-114">Este ejemplo se utiliza la <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> método y establece el `handledEventsToo` parámetro para `true` para que los controladores de eventos se invocará aunque el <xref:System.Windows.Controls.RichTextBox> marca estos eventos como controlado.</span><span class="sxs-lookup"><span data-stu-id="fccef-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="fccef-115">El código en los controladores de eventos agrega funcionalidad para abrir un archivo de texto que se coloca en el <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="fccef-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="fccef-116">Para probar este ejemplo, arrastre un archivo de texto o un archivo de texto enriquecido (RTF) formato desde el Explorador de Windows para el <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="fccef-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="fccef-117">El archivo se abrirá en el <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="fccef-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="fccef-118">Si presiona la tecla MAYÚS antes de la eliminación del archivo, se abrirá el archivo como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="fccef-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
