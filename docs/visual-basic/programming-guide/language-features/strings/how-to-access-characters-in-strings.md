---
description: 'Más información acerca de cómo: obtener acceso a caracteres en cadenas en Visual Basic'
title: Procedimiento para obtener acceso a caracteres de cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 373005699483dbae92df3a6fe73cc9b6318a9c61
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476168"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="46ce5-103">Cómo: Obtener acceso a caracteres de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46ce5-103">How to: Access Characters in Strings in Visual Basic</span></span>

<span data-ttu-id="46ce5-104">En este ejemplo se muestra cómo utilizar la <xref:System.String.Chars%2A> propiedad para tener acceso al carácter que se encuentra en la ubicación especificada de una cadena.</span><span class="sxs-lookup"><span data-stu-id="46ce5-104">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ce5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46ce5-105">Example</span></span>  

 <span data-ttu-id="46ce5-106">A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena.</span><span class="sxs-lookup"><span data-stu-id="46ce5-106">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="46ce5-107">Puede pensar en una cadena como una matriz de caracteres ( `Char` instancias); puede recuperar un carácter determinado haciendo referencia al índice de ese carácter a través de la <xref:System.String.Chars%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="46ce5-107">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="46ce5-108">El `index` parámetro de la <xref:System.String.Chars%2A> propiedad es de base cero.</span><span class="sxs-lookup"><span data-stu-id="46ce5-108">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="46ce5-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="46ce5-109">Robust Programming</span></span>  

 <span data-ttu-id="46ce5-110">La <xref:System.String.Chars%2A> propiedad devuelve el carácter que se encuentra en la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="46ce5-110">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="46ce5-111">Sin embargo, algunos caracteres Unicode pueden estar representados por más de un carácter.</span><span class="sxs-lookup"><span data-stu-id="46ce5-111">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="46ce5-112">Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: convertir una cadena en una matriz de caracteres](how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="46ce5-112">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="46ce5-113">La <xref:System.String.Chars%2A> propiedad produce una <xref:System.IndexOutOfRangeException> excepción si el `index` parámetro es mayor o igual que la longitud de la cadena, o si es menor que cero.</span><span class="sxs-lookup"><span data-stu-id="46ce5-113">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ce5-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46ce5-114">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="46ce5-115">Procedimiento para convertir una cadena en una matriz de caracteres</span><span class="sxs-lookup"><span data-stu-id="46ce5-115">How to: Convert a String to an Array of Characters</span></span>](how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="46ce5-116">Conversión entre cadenas y otros tipos de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46ce5-116">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="46ce5-117">Cadenas</span><span class="sxs-lookup"><span data-stu-id="46ce5-117">Strings</span></span>](index.md)
