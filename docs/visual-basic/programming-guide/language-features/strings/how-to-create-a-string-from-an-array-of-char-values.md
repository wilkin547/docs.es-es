---
title: 'Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 104b329011d69e10a2926f31ce5d296759a3cce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647185"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="9d60b-102">Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d60b-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="9d60b-103">Este ejemplo crea la cadena "abcd" de caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="9d60b-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d60b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d60b-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d60b-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9d60b-105">Compiling the Code</span></span>  
 <span data-ttu-id="9d60b-106">Este método no tiene ningún requisito especial.</span><span class="sxs-lookup"><span data-stu-id="9d60b-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="9d60b-107">La sintaxis `"a"c`, donde una sola `c` sigue un carácter individual entre comillas, se utiliza para crear un carácter literal.</span><span class="sxs-lookup"><span data-stu-id="9d60b-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9d60b-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9d60b-108">Robust Programming</span></span>  
 <span data-ttu-id="9d60b-109">Caracteres null (equivalente a `Chr(0)`) en la cadena de provocar resultados inesperados cuando se usa la cadena.</span><span class="sxs-lookup"><span data-stu-id="9d60b-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="9d60b-110">El carácter null se incluirá con la cadena, pero los caracteres que siguen el carácter null no se mostrará en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="9d60b-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d60b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d60b-111">See Also</span></span>  
 <xref:System.String>  
 [<span data-ttu-id="9d60b-112">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9d60b-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="9d60b-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9d60b-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
