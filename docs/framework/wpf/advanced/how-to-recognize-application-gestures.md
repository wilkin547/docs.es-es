---
title: Cómo Reconocer gestos en aplicaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 647e7c9c1d785cebfdc362dc48511d865f3945dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191515"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="d2689-102">Cómo Reconocer gestos en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d2689-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="d2689-103">En el ejemplo siguiente se muestra cómo borrar la entrada manuscrita cuando un usuario realiza una <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> de gestos en un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="d2689-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="d2689-104">En este ejemplo se da por supuesto un <xref:System.Windows.Controls.InkCanvas>, llamado `inkCanvas1`, se declara en el archivo XAML.</span><span class="sxs-lookup"><span data-stu-id="d2689-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2689-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2689-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d2689-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2689-106">See also</span></span>

- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
