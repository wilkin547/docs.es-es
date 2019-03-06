---
title: Filtrar Borrar la entrada manuscrita en un control personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365898"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="8d843-102">Procedimiento Borrar la entrada manuscrita en un control personalizado</span><span class="sxs-lookup"><span data-stu-id="8d843-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="8d843-103">El <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina si el trazo dibujado actualmente se cruza con otro trazo.</span><span class="sxs-lookup"><span data-stu-id="8d843-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="8d843-104">Esto es útil para crear un control que permite al usuario borrar partes de un trazo, la forma en que un usuario puede en un <xref:System.Windows.Controls.InkCanvas> cuando el <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> está establecido en <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span><span class="sxs-lookup"><span data-stu-id="8d843-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d843-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d843-105">Example</span></span>  
 <span data-ttu-id="8d843-106">El ejemplo siguiente crea un control personalizado que permite al usuario borrar partes de trazos.</span><span class="sxs-lookup"><span data-stu-id="8d843-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="8d843-107">En este ejemplo se crea un control que contiene la entrada de lápiz cuando se inicializa.</span><span class="sxs-lookup"><span data-stu-id="8d843-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="8d843-108">Para crear un control que recopila entradas de lápiz, consulte [creación de un Control de entrada manuscrita](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="8d843-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
