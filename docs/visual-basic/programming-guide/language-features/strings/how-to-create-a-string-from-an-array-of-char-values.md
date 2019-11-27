---
title: 'Cómo: Crear una cadena a partir de una matriz de caracteres'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 03138a851afc55f735cc66edeb345817428a0452
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344388"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="b2653-102">Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2653-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="b2653-103">En este ejemplo se crea la cadena "ABCD" a partir de caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="b2653-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2653-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2653-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2653-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b2653-105">Compiling the Code</span></span>  
 <span data-ttu-id="b2653-106">Este método no tiene requisitos especiales.</span><span class="sxs-lookup"><span data-stu-id="b2653-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="b2653-107">La sintaxis `"a"c`, donde un solo `c` sigue un carácter único entre comillas, se usa para crear un literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="b2653-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b2653-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b2653-108">Robust Programming</span></span>  
 <span data-ttu-id="b2653-109">Los caracteres nulos (equivalentes a `Chr(0)`) en la cadena conducen a resultados inesperados al usar la cadena.</span><span class="sxs-lookup"><span data-stu-id="b2653-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="b2653-110">El carácter nulo se incluirá con la cadena, pero los caracteres que siguen al carácter nulo no se mostrarán en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="b2653-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2653-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2653-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="b2653-112">Char (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="b2653-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="b2653-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="b2653-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
