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
# <a name="storing-ink"></a>Almacenar entradas manuscritas
El <xref:System.Windows.Ink.StrokeCollection.Save%2A> métodos proporcionan compatibilidad para almacenar la entrada manuscrita como formato serializado de tinta (ISF). Constructores para la <xref:System.Windows.Ink.StrokeCollection> clase proporcionan compatibilidad para leer los datos de tinta.  
  
## <a name="ink-storage-and-retrieval"></a>Almacenamiento de tinta y la recuperación  
 Esta sección describe cómo almacenar y recuperar entradas manuscritas en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] plataforma.  
  
 En el ejemplo siguiente se implementa un controlador de eventos de clic de botón que presenta al usuario un cuadro de diálogo Guardar archivo y guarda la tinta de una <xref:System.Windows.Controls.InkCanvas> fuera a un archivo.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 En el ejemplo siguiente se implementa un controlador de eventos de clic de botón que presenta al usuario un cuadro de diálogo Abrir archivo y lee la tinta del archivo en un <xref:System.Windows.Controls.InkCanvas> elemento.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.InkCanvas>  
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)
