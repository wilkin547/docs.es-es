---
title: "Cómo: Agregar un valor de salida de animación a un valor inicial de animación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1a6a5923655c5857b813df778b36b6c7fd208b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>Cómo: Agregar un valor de salida de animación a un valor inicial de animación
Este ejemplo muestra cómo agregar un valor de salida de animación a un valor de inicio de la animación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad especifica si desea que el valor de salida de una animación que se agrega al valor inicial (valor base) de una propiedad animada. Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad con animaciones más básicas y la mayoría de las animaciones de fotograma clave. Para obtener más información, consulte [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) y [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 En el ejemplo siguiente se muestra el efecto de usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimation> y el uso de la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Acumular valores de animaciones durante la repetición de ciclos](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Animación y temporización](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
