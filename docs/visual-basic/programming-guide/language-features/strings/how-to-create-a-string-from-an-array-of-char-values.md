---
title: 'Cómo: Crear una cadena a partir de una matriz de caracteres'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346769"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="fb2a5-102">Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb2a5-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="fb2a5-103">En este ejemplo se crea la cadena "ABCD" a partir de caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="fb2a5-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb2a5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb2a5-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="fb2a5-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fb2a5-105">Compile the code</span></span>  
 <span data-ttu-id="fb2a5-106">Este método no tiene requisitos especiales.</span><span class="sxs-lookup"><span data-stu-id="fb2a5-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="fb2a5-107">La sintaxis `"a"c`, donde un solo `c` sigue un carácter único entre comillas, se usa para crear un literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="fb2a5-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fb2a5-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="fb2a5-108">Robust Programming</span></span>  
 <span data-ttu-id="fb2a5-109">Los caracteres nulos (equivalentes a `Chr(0)`) en la cadena conducen a resultados inesperados al usar la cadena.</span><span class="sxs-lookup"><span data-stu-id="fb2a5-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="fb2a5-110">El carácter nulo se incluirá con la cadena, pero los caracteres que siguen al carácter nulo no se mostrarán en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="fb2a5-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2a5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb2a5-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="fb2a5-112">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="fb2a5-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="fb2a5-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="fb2a5-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
