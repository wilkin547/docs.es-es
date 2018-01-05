---
title: "Cómo: Utilizar un objeto MatrixTransform para crear transformaciones personalizadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1414ae590be10c3adcc6857492e23bf659beec67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="39146-102">Cómo: Utilizar un objeto MatrixTransform para crear transformaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="39146-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="39146-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.MatrixTransform> traslación (movimiento) la posición, expandir y contraer de un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="39146-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39146-104">Use la <xref:System.Windows.Media.MatrixTransform> clase para crear transformaciones personalizadas que no se proporcionan con el <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, o <xref:System.Windows.Media.TranslateTransform> clases.</span><span class="sxs-lookup"><span data-stu-id="39146-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39146-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39146-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="39146-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="39146-106">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="39146-107">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="39146-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="39146-108">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="39146-108">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="39146-109">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="39146-109">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
