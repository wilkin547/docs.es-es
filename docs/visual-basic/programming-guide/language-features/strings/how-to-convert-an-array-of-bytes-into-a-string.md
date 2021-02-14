---
description: 'Más información sobre: Cómo: convertir una matriz de bytes en una cadena en Visual Basic'
title: Procedimiento para convertir una matriz de bytes en una cadena
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: ded4a2c4c235e560198ef2edd4c5031141554079
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425573"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Cómo: Convertir una matriz de bytes en una cadena en Visual Basic

En este tema se muestra cómo convertir los bytes de una matriz de bytes en una cadena.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa el <xref:System.Text.Encoding.GetString%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase Encoding para convertir todos los bytes de una matriz de bytes en una cadena.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 Puede elegir entre varias opciones de codificación para convertir una matriz de bytes en una cadena:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (7 bits).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Cómo: Convertir cadenas en una matriz de bytes en Visual Basic](how-to-convert-strings-into-an-array-of-bytes.md)
