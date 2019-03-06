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
ms.openlocfilehash: a4c38ddf52e9054fe9126df4b7e172548617b90d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375485"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="359ea-102">Filtrar Analizar entradas manuscritas con sugerencias de análisis</span><span class="sxs-lookup"><span data-stu-id="359ea-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="359ea-103">Un [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) proporciona una sugerencia para el [la clase System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) al que está asociado.</span><span class="sxs-lookup"><span data-stu-id="359ea-103">An [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) to which it is attached.</span></span>  <span data-ttu-id="359ea-104">La sugerencia se aplica al área especificado por el [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) propiedad de la [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) y proporciona contexto adicional para el analizador de tinta a mejorar la precisión del reconocimiento.</span><span class="sxs-lookup"><span data-stu-id="359ea-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) property of the [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="359ea-105">El [la clase System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) se aplica esta información de contexto al analizar la entrada manuscrita obtenida en el área de la sugerencia.</span><span class="sxs-lookup"><span data-stu-id="359ea-105">The [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="359ea-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="359ea-106">Example</span></span>  
 <span data-ttu-id="359ea-107">El ejemplo siguiente es una aplicación que usa varios [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objetos en un formulario que acepta la entrada de lápiz.</span><span class="sxs-lookup"><span data-stu-id="359ea-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objects on a form that accepts ink input.</span></span> <span data-ttu-id="359ea-108">La aplicación usa el [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) propiedad para proporcionar información de contexto para cada entrada en el formulario.</span><span class="sxs-lookup"><span data-stu-id="359ea-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="359ea-109">La aplicación utiliza el análisis en segundo plano para analizar la entrada de lápiz y borra el formulario de todas las entradas manuscritas en cinco segundos después de que el usuario detiene la adición de tinta.</span><span class="sxs-lookup"><span data-stu-id="359ea-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
