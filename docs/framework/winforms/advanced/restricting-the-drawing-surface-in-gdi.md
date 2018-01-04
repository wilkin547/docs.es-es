---
title: Limitar la superficie de dibujo en GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7834c95959972e7264e1caa2cfc21b190341b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Limitar la superficie de dibujo en GDI+
Recortar implica la restricción del dibujo a un rectángulo o una región determinados. La siguiente ilustración muestra la cadena "Hello" recortada en una región en forma de corazón.  
  
 ![Superficie de dibujo restringida](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Recorte con regiones  
 Se pueden construir regiones desde rutas de acceso y las rutas de acceso pueden contener los contornos de cadenas, por lo que puede utilizar texto con contorno para recortar. En la siguiente ilustración muestra un conjunto de elipses concéntricas recortadas en el interior de una cadena de texto.  
  
 ![Superficie de dibujo restringida](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Para dibujar con recorte, crear un <xref:System.Drawing.Graphics> de objetos, establecer su <xref:System.Drawing.Graphics.Clip%2A> propiedad y, a continuación, llame a los métodos de dibujo de ese mismo <xref:System.Drawing.Graphics> objeto:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Utilizar regiones](../../../../docs/framework/winforms/advanced/using-regions.md)
