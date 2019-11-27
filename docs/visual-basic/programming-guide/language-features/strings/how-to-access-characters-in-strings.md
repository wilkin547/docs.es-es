---
title: 'Cómo: Obtener acceso a caracteres de cadenas'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352459"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="15217-102">Cómo: Obtener acceso a caracteres de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15217-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="15217-103">En este ejemplo se muestra cómo utilizar la propiedad <xref:System.String.Chars%2A> para tener acceso al carácter que se encuentra en la ubicación especificada de una cadena.</span><span class="sxs-lookup"><span data-stu-id="15217-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15217-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15217-104">Example</span></span>  
 <span data-ttu-id="15217-105">A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena.</span><span class="sxs-lookup"><span data-stu-id="15217-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="15217-106">Puede pensar en una cadena como una matriz de caracteres (instancias`Char`); puede recuperar un carácter determinado haciendo referencia al índice de ese carácter a través de la propiedad <xref:System.String.Chars%2A>.</span><span class="sxs-lookup"><span data-stu-id="15217-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="15217-107">El parámetro `index` de la propiedad <xref:System.String.Chars%2A> está basado en cero.</span><span class="sxs-lookup"><span data-stu-id="15217-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="15217-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="15217-108">Robust Programming</span></span>  
 <span data-ttu-id="15217-109">La propiedad <xref:System.String.Chars%2A> devuelve el carácter que se encuentra en la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="15217-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="15217-110">Sin embargo, algunos caracteres Unicode pueden estar representados por más de un carácter.</span><span class="sxs-lookup"><span data-stu-id="15217-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="15217-111">Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="15217-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="15217-112">La propiedad <xref:System.String.Chars%2A> produce una excepción <xref:System.IndexOutOfRangeException> si el parámetro `index` es mayor o igual que la longitud de la cadena, o si es menor que cero.</span><span class="sxs-lookup"><span data-stu-id="15217-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15217-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="15217-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="15217-114">Convertir una cadena en una matriz de caracteres</span><span class="sxs-lookup"><span data-stu-id="15217-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="15217-115">Conversión entre cadenas y otros tipos de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15217-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="15217-116">Cadenas</span><span class="sxs-lookup"><span data-stu-id="15217-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
