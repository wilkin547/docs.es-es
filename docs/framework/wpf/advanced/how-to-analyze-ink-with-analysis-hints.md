---
title: Filtrar Analizar entradas manuscritas con sugerencias de análisis
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: c0071620c406c5907bbb656269729a5aad98eede
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748679"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a>Filtrar Analizar entradas manuscritas con sugerencias de análisis
Un [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) proporciona una sugerencia para el [la clase System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) al que está asociado.  La sugerencia se aplica al área especificado por el [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) propiedad de la [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) y proporciona contexto adicional para el analizador de tinta a mejorar la precisión del reconocimiento. El [la clase System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) se aplica esta información de contexto al analizar la entrada manuscrita obtenida en el área de la sugerencia.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es una aplicación que usa varios [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objetos en un formulario que acepta la entrada de lápiz. La aplicación usa el [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) propiedad para proporcionar información de contexto para cada entrada en el formulario.  La aplicación utiliza el análisis en segundo plano para analizar la entrada de lápiz y borra el formulario de todas las entradas manuscritas en cinco segundos después de que el usuario detiene la adición de tinta.  
  
 [!code-xaml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
