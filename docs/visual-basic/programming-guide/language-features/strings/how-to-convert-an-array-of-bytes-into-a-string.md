---
title: 'Cómo: Convertir una matriz de bytes en una cadena en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: c22ae89322230d8a98ae3ae2c1485e73456e0a7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648979"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Cómo: Convertir una matriz de bytes en una cadena en Visual Basic
Este tema muestra cómo convertir los bytes de una matriz de bytes en una cadena.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la <xref:System.Text.Encoding.GetString%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase para convertir todos los bytes de una matriz de bytes en una cadena de codificación.  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 Se puede elegir entre varias opciones de codificación para convertir una matriz de bytes en una cadena:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el carácter de ASCII (7 bits) establecidas.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes little-endian.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes little-endian.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetString%2A>  
 [Cómo: convertir cadenas en una matriz de Bytes en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
