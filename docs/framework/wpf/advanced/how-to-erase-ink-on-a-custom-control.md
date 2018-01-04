---
title: "Cómo: Borrar la entrada manuscrita en un control personalizado"
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
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e05163bcbafd360e0929fe784ff1111bd0663ef3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Cómo: Borrar la entrada manuscrita en un control personalizado
El <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina si el trazo dibujado actualmente se cruza con otro trazo.  Esto es útil para crear un control que permite al usuario borrar partes de un trazo, la forma en que un usuario puede en un <xref:System.Windows.Controls.InkCanvas> cuando el <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> está establecido en <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un control personalizado que permite al usuario borrar partes de trazos.  En este ejemplo se crea un control que contiene la entrada de lápiz cuando se inicializa.  Para crear un control que recopile tinta, consulte [crear un Control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
