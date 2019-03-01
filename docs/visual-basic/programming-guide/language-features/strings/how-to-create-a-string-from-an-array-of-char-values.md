---
title: Procedimiento Crear una cadena de una matriz de valores Char (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 0d3a4caf0967ab77de7d91470e43e52521dbd2da
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975516"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="9c6ff-102">Filtrar Crear una cadena de una matriz de valores Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c6ff-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="9c6ff-103">Este ejemplo crea la cadena "abcd" de caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="9c6ff-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c6ff-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c6ff-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c6ff-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9c6ff-105">Compiling the Code</span></span>  
 <span data-ttu-id="9c6ff-106">Este método no tiene ningún requisito especial.</span><span class="sxs-lookup"><span data-stu-id="9c6ff-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="9c6ff-107">La sintaxis `"a"c`, donde una sola `c` sigue un solo carácter entre comillas, se usa para crear un carácter literal.</span><span class="sxs-lookup"><span data-stu-id="9c6ff-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9c6ff-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9c6ff-108">Robust Programming</span></span>  
 <span data-ttu-id="9c6ff-109">Caracteres nulos (equivalente a `Chr(0)`) en la cadena de provocar resultados inesperados cuando se usa la cadena.</span><span class="sxs-lookup"><span data-stu-id="9c6ff-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="9c6ff-110">El carácter nulo se incluirá con la cadena, pero no se mostrará después del carácter nulo de caracteres en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="9c6ff-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6ff-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c6ff-111">See also</span></span>
- <xref:System.String>
- [<span data-ttu-id="9c6ff-112">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9c6ff-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="9c6ff-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9c6ff-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
