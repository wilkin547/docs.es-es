---
title: Almacenar entradas manuscritas
ms.date: 03/30/2017
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
ms.openlocfilehash: 4089aa7942105c14eb628c75edb7f53ffacfaeb0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182343"
---
# <a name="storing-ink"></a>Almacenar entradas manuscritas
El <xref:System.Windows.Ink.StrokeCollection.Save%2A> métodos proporcionan compatibilidad para almacenar entradas manuscritas como formato serializado de tinta (ISF). Los constructores para la <xref:System.Windows.Ink.StrokeCollection> clase proporcionan compatibilidad para leer los datos de entrada de lápiz.  
  
## <a name="ink-storage-and-retrieval"></a>Almacenamiento de tinta y la recuperación  
 Esta sección describe cómo almacenar y recuperar entradas manuscritas en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] plataforma.  
  
 El ejemplo siguiente implementa un controlador de eventos de clic de botón que presenta al usuario un cuadro de diálogo Guardar archivo y guarda la tinta de una <xref:System.Windows.Controls.InkCanvas> fuera a un archivo.  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 El ejemplo siguiente implementa un controlador de eventos de clic de botón que presenta al usuario un cuadro de diálogo Abrir archivo y lee la entrada de lápiz del archivo en un <xref:System.Windows.Controls.InkCanvas> elemento.  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.InkCanvas>
- [Windows Presentation Foundation](../index.md)
