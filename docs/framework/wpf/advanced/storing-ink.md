---
title: Almacenar entradas manuscritas
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
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 244a4bfa5def1319438d66a52120e36aab0e753b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="storing-ink"></a><span data-ttu-id="8585c-102">Almacenar entradas manuscritas</span><span class="sxs-lookup"><span data-stu-id="8585c-102">Storing Ink</span></span>
<span data-ttu-id="8585c-103">El <xref:System.Windows.Ink.StrokeCollection.Save%2A> métodos proporcionan compatibilidad para almacenar la entrada manuscrita como formato serializado de tinta (ISF).</span><span class="sxs-lookup"><span data-stu-id="8585c-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="8585c-104">Constructores para la <xref:System.Windows.Ink.StrokeCollection> clase proporcionan compatibilidad para leer los datos de tinta.</span><span class="sxs-lookup"><span data-stu-id="8585c-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="8585c-105">Almacenamiento de tinta y la recuperación</span><span class="sxs-lookup"><span data-stu-id="8585c-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="8585c-106">Esta sección describe cómo almacenar y recuperar entradas manuscritas en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] plataforma.</span><span class="sxs-lookup"><span data-stu-id="8585c-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="8585c-107">En el ejemplo siguiente se implementa un controlador de eventos de clic de botón que presenta al usuario un cuadro de diálogo Guardar archivo y guarda la tinta de una <xref:System.Windows.Controls.InkCanvas> fuera a un archivo.</span><span class="sxs-lookup"><span data-stu-id="8585c-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="8585c-108">En el ejemplo siguiente se implementa un controlador de eventos de clic de botón que presenta al usuario un cuadro de diálogo Abrir archivo y lee la tinta del archivo en un <xref:System.Windows.Controls.InkCanvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="8585c-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="8585c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8585c-109">See Also</span></span>  
 <xref:System.Windows.Controls.InkCanvas>  
 [<span data-ttu-id="8585c-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="8585c-110">Windows Presentation Foundation</span></span>](../../../../docs/framework/wpf/index.md)
