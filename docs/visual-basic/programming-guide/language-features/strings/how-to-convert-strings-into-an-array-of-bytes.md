---
description: 'Más información sobre: Cómo: convertir cadenas en una matriz de bytes en Visual Basic'
title: Procedimiento para convertir cadenas en una matriz de bytes
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: edd41bc1dd7026c5b4ed061211f4b7884cd6044a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429851"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="cb9c9-103">Cómo: Convertir cadenas en una matriz de bytes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb9c9-103">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>

<span data-ttu-id="cb9c9-104">En este tema se muestra cómo convertir una cadena en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-104">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb9c9-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb9c9-105">Example</span></span>  

 <span data-ttu-id="cb9c9-106">En este ejemplo se usa el <xref:System.Text.Encoding.GetBytes%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase Encoding para convertir una cadena en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-106">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="cb9c9-107">Puede elegir entre varias opciones de codificación para convertir una cadena en una matriz de bytes:</span><span class="sxs-lookup"><span data-stu-id="cb9c9-107">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="cb9c9-108"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="cb9c9-108"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="cb9c9-109"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-109"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="cb9c9-110"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-110"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="cb9c9-111"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-111"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="cb9c9-112"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-112"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="cb9c9-113"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-113"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="cb9c9-114"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="cb9c9-114"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9c9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb9c9-115">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="cb9c9-116">Cómo: Convertir una matriz de bytes en una cadena en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb9c9-116">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](how-to-convert-an-array-of-bytes-into-a-string.md)
