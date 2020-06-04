---
title: Procedimiento para crear una cadena a partir de una matriz de valores de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: d9ec897467f0caac0afc089a028516c0316a2bda
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410598"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="3c66b-102">Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c66b-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="3c66b-103">En este ejemplo se crea la cadena "ABCD" a partir de caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="3c66b-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c66b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c66b-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="3c66b-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3c66b-105">Compile the code</span></span>  
 <span data-ttu-id="3c66b-106">Este método no tiene requisitos especiales.</span><span class="sxs-lookup"><span data-stu-id="3c66b-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="3c66b-107">La sintaxis `"a"c` , en la que un solo `c` carácter sigue a un solo carácter entre comillas, se usa para crear un literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="3c66b-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3c66b-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="3c66b-108">Robust Programming</span></span>  
 <span data-ttu-id="3c66b-109">Los caracteres nulos (equivalentes a `Chr(0)` ) de la cadena conducen a resultados inesperados al usar la cadena.</span><span class="sxs-lookup"><span data-stu-id="3c66b-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="3c66b-110">El carácter nulo se incluirá con la cadena, pero los caracteres que siguen al carácter nulo no se mostrarán en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="3c66b-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c66b-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c66b-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="3c66b-112">Tipo de datos Char</span><span class="sxs-lookup"><span data-stu-id="3c66b-112">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="3c66b-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="3c66b-113">Data Types</span></span>](../data-types/index.md)
