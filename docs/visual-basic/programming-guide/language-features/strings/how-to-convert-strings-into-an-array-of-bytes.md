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
ms.openlocfilehash: d9a5a329a82555e66a391fd93005634106569232
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071188"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="f3909-102">Cómo: Convertir cadenas en una matriz de bytes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3909-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>

<span data-ttu-id="f3909-103">En este tema se muestra cómo convertir una cadena en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="f3909-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3909-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3909-104">Example</span></span>  

 <span data-ttu-id="f3909-105">En este ejemplo se usa el <xref:System.Text.Encoding.GetBytes%2A> método de la <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> clase Encoding para convertir una cadena en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="f3909-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="f3909-106">Puede elegir entre varias opciones de codificación para convertir una cadena en una matriz de bytes:</span><span class="sxs-lookup"><span data-stu-id="f3909-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="f3909-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Obtiene una codificación para el juego de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="f3909-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="f3909-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="f3909-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="f3909-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Obtiene una codificación para la página de códigos ANSI actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="f3909-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="f3909-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-16 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="f3909-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="f3909-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-32 utilizando el orden de bytes Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="f3909-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="f3909-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="f3909-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="f3909-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Obtiene una codificación para el formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f3909-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3909-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3909-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="f3909-115">Cómo: Convertir una matriz de bytes en una cadena en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3909-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](how-to-convert-an-array-of-bytes-into-a-string.md)
