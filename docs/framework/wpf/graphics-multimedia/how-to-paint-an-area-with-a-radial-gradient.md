---
title: Procedimiento Pintar un área con un degradado radial
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 5762ef1a1526ba6f004917c8a947e35ce731c86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916098"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Procedimiento Pintar un área con un degradado radial
En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.RadialGradientBrush> la clase para pintar un área con un degradado radial.  
  
## <a name="example"></a>Ejemplo  
 <xref:System.Windows.Media.RadialGradientBrush> En el ejemplo siguiente se usa para pintar un rectángulo con un degradado radial que realiza la transición de amarillo a rojo a azul a verde lima.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 En la ilustración siguiente se muestra el degradado del ejemplo anterior. Los topes del degradado se han resaltado.  
  
 ![Delimitadores de degradado en un degradado radial](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
> En los ejemplos de este tema se usa el sistema de coordenadas predeterminado para establecer los puntos de control. El sistema de coordenadas predeterminado es relativo a un cuadro de límite: 0 indica un 0 por ciento del rectángulo de selección, mientras que 1 indica un 100 por cien del rectángulo de selección. Puede cambiar este sistema de coordenadas estableciendo la <xref:System.Windows.Media.GradientBrush.MappingMode%2A> propiedad en el valor. <xref:System.Windows.Media.BrushMappingMode.Absolute> Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección. Los valores se interpretan directamente en el espacio local.  
  
 Para obtener <xref:System.Windows.Media.RadialGradientBrush> más ejemplos, vea el [ejemplo brushes](https://go.microsoft.com/fwlink/?LinkID=159973). Para obtener más información sobre los degradados y otros tipos de pinceles, consulte [información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).
