---
title: 'Cómo: convertir una matriz de bytes en una cadena'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 8c1d9d1d2e89390873bc1c3dbb9623f047433a9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351986"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Cómo: Convertir una matriz de bytes en una cadena en Visual Basic
En este tema se muestra cómo convertir los bytes de una matriz de bytes en una cadena.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el método <xref:System.Text.Encoding.GetString%2A> de la clase de codificación <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> para convertir todos los bytes de una matriz de bytes en una cadena.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 Puede elegir entre varias opciones de codificación para convertir una matriz de bytes en una cadena:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: obtiene una codificación para el juego de caracteres ASCII (7 bits).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: obtiene una codificación para el formato UTF-8.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Cómo: convertir cadenas en una matriz de bytes en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
