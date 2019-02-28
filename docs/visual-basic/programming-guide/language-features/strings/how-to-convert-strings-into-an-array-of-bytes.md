---
title: Filtrar Convertir cadenas en una matriz de Bytes en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: a96664f308a711d440f063627665283c5b7fc264
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967508"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Procedimiento Convertir cadenas en una matriz de Bytes en Visual Basic
En este tema se muestra cómo convertir una cadena en una matriz de bytes.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Text.Encoding.GetBytes%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase para convertir una cadena en una matriz de bytes de codificación.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 Puede elegir entre varias opciones de codificación para convertir una cadena en una matriz de bytes:  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (de 7 bits).  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes little-endian.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes little-endian.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Cómo: Convertir una matriz de Bytes en una cadena en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
