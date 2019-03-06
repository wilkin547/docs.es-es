---
title: Filtrar Animar una propiedad sin utilizar un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: b76afeb0187065ff07c832363d3a52896aa36822
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371173"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Filtrar Animar una propiedad sin utilizar un guión gráfico
En este ejemplo se muestra una manera de aplicar una animación a una propiedad sin utilizar un <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  Esta funcionalidad no está disponible en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Para información sobre cómo animar una propiedad en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vea [Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Para aplicar una animación local a una propiedad, utilice el <xref:System.Windows.UIElement.BeginAnimation%2A> método. Este método toma dos parámetros: un <xref:System.Windows.DependencyProperty> que especifica la propiedad que se va a animar y la animación que se aplican a esa propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo animar el color de fondo y de ancho de un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Una variedad de clases de animación en el <xref:System.Windows.Media.Animation> existe espacio de nombres para animar diferentes tipos de propiedades. Para más información sobre la animación de propiedades, vea [Información general sobre animaciones](animation-overview.md). Para más información sobre las propiedades de dependencia (el tipo de propiedades que se muestran en estos ejemplos) y sus características, vea [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).  
  
 Hay otras maneras de animar sin utilizar <xref:System.Windows.Media.Animation.Storyboard> objetos; para obtener más información, consulte [técnicas de animación de información general sobre propiedades](property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
- [Información general sobre animaciones](animation-overview.md)
