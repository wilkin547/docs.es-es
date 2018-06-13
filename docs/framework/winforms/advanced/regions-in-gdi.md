---
title: Regiones de GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: dc7f10571163d447802c90cd61d71b11d0e695d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524588"
---
# <a name="regions-in-gdi"></a>Regiones de GDI+
Una región es una parte del área de presentación de un dispositivo de salida. Las regiones pueden ser simples (un único rectángulo) o complejas (una combinación de polígonos y curvas cerradas). En la siguiente ilustración se muestra dos regiones: una construida a partir de un rectángulo y la otra construida a partir de una ruta de acceso.  
  
 ![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Utilizar regiones  
 Las regiones se utilizan a menudo para recortar y la prueba de posicionamiento. Recortar implica la restricción del dibujo a una región determinada del área de presentación, normalmente la parte que debe actualizarse. La prueba de posicionamiento implica la comprobación para determinar si el cursor está en una región determinada de la pantalla cuando se presiona un botón del mouse.  
  
 Puede construir una región de un rectángulo o una ruta de acceso. También puede crear regiones complejas mediante la combinación de regiones existentes. El <xref:System.Drawing.Region> clase proporciona los siguientes métodos para combinar regiones: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, y <xref:System.Drawing.Region.Complement%2A>.  
  
 La intersección de dos regiones es el conjunto de todos los puntos que pertenecen a ambas regiones. La unión es el conjunto de todos los puntos que pertenecen a una u otra materia o ambas regiones. El complemento de una región es el conjunto de todos los puntos que no están en la región. En la siguiente ilustración muestra la intersección y la unión de las dos regiones que se muestra en la ilustración anterior.  
  
 ![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 El <xref:System.Drawing.Region.Xor%2A> método, que se aplique a un par de regiones, genera una región que contiene todos los puntos que pertenecen a una región o la otra, pero no ambos. El <xref:System.Drawing.Region.Exclude%2A> método, que se aplique a un par de regiones, genera una región que contiene todos los puntos de la primera región que no están en la segunda región. En la siguiente ilustración se muestra las regiones que son el resultado de aplicar el <xref:System.Drawing.Region.Xor%2A> y <xref:System.Drawing.Region.Exclude%2A> métodos a las dos regiones mostradas al principio de este tema.  
  
 ![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Para rellenar una región, son necesarios un <xref:System.Drawing.Graphics> objeto, un <xref:System.Drawing.Brush> objeto y un <xref:System.Drawing.Region> objeto. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.FillRegion%2A> método y el <xref:System.Drawing.Brush> objeto almacena atributos del relleno, como el color o una trama. En el ejemplo siguiente se rellena una región con un color sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Utilizar regiones](../../../../docs/framework/winforms/advanced/using-regions.md)
