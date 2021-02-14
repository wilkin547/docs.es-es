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
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="ccb8b-103">Cómo: Convertir una matriz de bytes en una cadena en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccb8b-103">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>

<span data-ttu-id="ccb8b-104">En este tema se muestra cómo convertir los bytes de una matriz de bytes en una cadena.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-104">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccb8b-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccb8b-105">Example</span></span>  

 <span data-ttu-id="ccb8b-106">En este ejemplo se usa el <xref:System.Text.Encoding.GetString%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase Encoding para convertir todos los bytes de una matriz de bytes en una cadena.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-106">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="ccb8b-107">Puede elegir entre varias opciones de codificación para convertir una matriz de bytes en una cadena:</span><span class="sxs-lookup"><span data-stu-id="ccb8b-107">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="ccb8b-108"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="ccb8b-108"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="ccb8b-109"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-109"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="ccb8b-110"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-110"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="ccb8b-111"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-111"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ccb8b-112"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-112"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ccb8b-113"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-113"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="ccb8b-114"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ccb8b-114"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb8b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ccb8b-115">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="ccb8b-116">Cómo: Convertir cadenas en una matriz de bytes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccb8b-116">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](how-to-convert-strings-into-an-array-of-bytes.md)
