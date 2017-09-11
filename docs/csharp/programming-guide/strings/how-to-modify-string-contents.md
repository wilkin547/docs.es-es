---
title: "Cómo: Modificar el contenido de cadenas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 114b6fdabd235d7e57947e77b672352e28aff11e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="5335c-102">Cómo: Modificar el contenido de cadenas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5335c-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="5335c-103">Como las cadenas son *immutables*, no es posible (sin usar código no seguro) modificar el valor de un objeto de cadena después de que se haya creado.</span><span class="sxs-lookup"><span data-stu-id="5335c-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="5335c-104">En cambio, existen muchas maneras de modificar el valor de una cadena y almacenar el resultado en un nuevo objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="5335c-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="5335c-105">La clase <xref:System.String?displayProperty=fullName> proporciona métodos que funcionan en una cadena de entrada y devuelven un nuevo objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="5335c-105">The <xref:System.String?displayProperty=fullName> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="5335c-106">En muchos casos, puede asignar el nuevo objeto a la variable que contenía la cadena original.</span><span class="sxs-lookup"><span data-stu-id="5335c-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="5335c-107">La clase <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> proporciona métodos adicionales que funcionan de una manera similar.</span><span class="sxs-lookup"><span data-stu-id="5335c-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="5335c-108">La clase <xref:System.Text.StringBuilder?displayProperty=fullName> proporciona un búfer de caracteres que puede modificar "en contexto".</span><span class="sxs-lookup"><span data-stu-id="5335c-108">The <xref:System.Text.StringBuilder?displayProperty=fullName> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="5335c-109">Puede llamar al método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> para crear un nuevo objeto de cadena que contiene el contenido actual del búfer.</span><span class="sxs-lookup"><span data-stu-id="5335c-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5335c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5335c-110">Example</span></span>  
 <span data-ttu-id="5335c-111">En el ejemplo siguiente se muestran varias maneras de reemplazar o quitar subcadenas en una cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="5335c-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 <span data-ttu-id="5335c-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5335c-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5335c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5335c-113">Example</span></span>  
 <span data-ttu-id="5335c-114">Para tener acceso a los caracteres individuales en una cadena mediante la notación de matriz, puede usar el objeto <xref:System.Text.StringBuilder>, que sobrecarga el operador `[]` para proporcionar acceso a su búfer de caracteres interno.</span><span class="sxs-lookup"><span data-stu-id="5335c-114">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="5335c-115">También puede convertir la cadena en una matriz de caracteres mediante el método <xref:System.String.ToCharArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="5335c-115">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="5335c-116">En el ejemplo siguiente se usa `ToCharArray` para crear la matriz.</span><span class="sxs-lookup"><span data-stu-id="5335c-116">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="5335c-117">Algunos elementos de esta matriz se modifican después.</span><span class="sxs-lookup"><span data-stu-id="5335c-117">Some elements of this array are then modified.</span></span> <span data-ttu-id="5335c-118">Un constructor de cadena que toma una matriz de caracteres como un parámetro de entrada se llama después para crear una nueva cadena.</span><span class="sxs-lookup"><span data-stu-id="5335c-118">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 <span data-ttu-id="5335c-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5335c-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5335c-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5335c-120">Example</span></span>  
 <span data-ttu-id="5335c-121">El ejemplo siguiente se proporciona para esas situaciones poco habituales en las que puede que quiera modificar una cadena en contexto mediante código no seguro de una manera similar a matrices de caracteres de estilo C.</span><span class="sxs-lookup"><span data-stu-id="5335c-121">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="5335c-122">El ejemplo muestra cómo tener acceso a los caracteres individuales "en contexto" con la palabra clave fixed.</span><span class="sxs-lookup"><span data-stu-id="5335c-122">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="5335c-123">También muestra un posible efecto secundario de operaciones no seguras en cadenas que se obtienen de la manera en que el compilador de C# almacena cadenas (internos) internamente.</span><span class="sxs-lookup"><span data-stu-id="5335c-123">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="5335c-124">En general, no debe usar esta técnica a no ser que sea absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="5335c-124">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 <span data-ttu-id="5335c-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5335c-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5335c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5335c-126">See Also</span></span>  
 <span data-ttu-id="5335c-127">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5335c-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5335c-128">Cadenas</span><span class="sxs-lookup"><span data-stu-id="5335c-128">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

