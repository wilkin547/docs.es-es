---
title: "Cómo: Pintar un área con un degradado radial"
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
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1da933a2ee7c179a55da7d33c61539d440eabc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Cómo: Pintar un área con un degradado radial
Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.RadialGradientBrush> clase para pintar un área con un degradado radial.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RadialGradientBrush> para dibujar un rectángulo con un degradado radial que cambia de amarillo a rojo a azul para Lima verde.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 En la siguiente ilustración muestra el degradado del ejemplo anterior. Se han resaltado del degradado.  
  
 ![Delimitadores de degradado en un degradado radial](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
>  Los ejemplos en este tema usan el sistema de coordenadas predeterminado para establecer puntos de control. El sistema de coordenadas predeterminado es relativo a un cuadro de límite: 0 indica un 0 por ciento del cuadro de límite y 1 indica un 100 por cien del cuadro de límite. Puede cambiar este sistema de coordenadas estableciendo la <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>. Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección. Los valores se interpretan directamente en el espacio local.  
  
 Para más <xref:System.Windows.Media.RadialGradientBrush> ejemplos, vea el [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973). Para obtener más información acerca de los degradados y otros tipos de pinceles, consulte [pintar con colores sólidos y degradados información general sobre](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
