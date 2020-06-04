---
title: Procedimiento para convertir cadenas en una matriz de bytes
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 3ee1d5e1e31054f23f4510c7a112d8e3473bcdd7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410611"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>Cómo: Convertir cadenas en una matriz de bytes en Visual Basic
En este tema se muestra cómo convertir una cadena en una matriz de bytes.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el <xref:System.Text.Encoding.GetBytes%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase Encoding para convertir una cadena en una matriz de bytes.  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 Puede elegir entre varias opciones de codificación para convertir una cadena en una matriz de bytes:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (7 bits).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [Cómo: Convertir una matriz de bytes en una cadena en Visual Basic](how-to-convert-an-array-of-bytes-into-a-string.md)
