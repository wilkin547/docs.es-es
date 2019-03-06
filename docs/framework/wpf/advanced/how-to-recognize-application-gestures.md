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
ms.openlocfilehash: 99deaa528a089f2d16268747f2e946873f3420a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370519"
---
# <a name="how-to-recognize-application-gestures"></a>Cómo Reconocer gestos en aplicaciones
En el ejemplo siguiente se muestra cómo borrar la entrada manuscrita cuando un usuario realiza una <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> de gestos en un <xref:System.Windows.Controls.InkCanvas>. En este ejemplo se da por supuesto un <xref:System.Windows.Controls.InkCanvas>, llamado `inkCanvas1`, se declara en el archivo XAML.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
