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
# <a name="how-to-erase-ink-on-a-custom-control"></a>Procedimiento Borrar la entrada manuscrita en un control personalizado
El <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina si el trazo dibujado actualmente se cruza con otro trazo.  Esto es útil para crear un control que permite al usuario borrar partes de un trazo, la forma en que un usuario puede en un <xref:System.Windows.Controls.InkCanvas> cuando el <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> está establecido en <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un control personalizado que permite al usuario borrar partes de trazos.  En este ejemplo se crea un control que contiene la entrada de lápiz cuando se inicializa.  Para crear un control que recopila entradas de lápiz, consulte [creación de un Control de entrada manuscrita](creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
