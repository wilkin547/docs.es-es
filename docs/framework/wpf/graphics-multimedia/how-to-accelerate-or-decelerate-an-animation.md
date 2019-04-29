---
title: Procedimiento Aumentar o reducir la velocidad de una animación
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: d4fcaf4a684c37590f27d603ef5cb2c86a6fb854
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762168"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a>Procedimiento Aumentar o reducir la velocidad de una animación
En este ejemplo se muestra cómo realizar una animación acelerar y reducir la velocidad con el tiempo. En el ejemplo siguiente, se animan los rectángulos varios por animaciones con diferentes <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> y <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> configuración.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 Se ha omitido el código en este ejemplo. Para el código completo, vea el [comportamiento de tiempo de animación (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) o [comportamiento de tiempo de animación (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).
