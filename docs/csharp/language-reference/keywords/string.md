---
title: string (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: f92a44283e59bd80421758a63b40bc5289c3628b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="string-c-reference"></a><span data-ttu-id="3ca7e-102">string (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3ca7e-102">string (C# Reference)</span></span>
<span data-ttu-id="3ca7e-103">El tipo `string` representa una secuencia de cero o más caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="3ca7e-104">`string` es un alias de <xref:System.String> en .NET.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-104">`string` is an alias for <xref:System.String> in .NET.</span></span>  
  
 <span data-ttu-id="3ca7e-105">Aunque `string` es un tipo de referencia, se definen los operadores de igualdad (`==` y `!=`) para comparar los valores de los objetos `string`, no las referencias.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="3ca7e-106">Esto hace que las pruebas de igualdad entre cadenas sean más intuitivas.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="3ca7e-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="3ca7e-108">Se muestra "True" y luego "False" porque el contenido de las cadenas es equivalente, pero `a` y `b` no hacen referencia a la misma instancia de cadena.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="3ca7e-109">El operador + concatena cadenas:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="3ca7e-110">Crea un objeto de cadena que contiene "good morning".</span><span class="sxs-lookup"><span data-stu-id="3ca7e-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="3ca7e-111">Las cadenas son *inmutables*: el contenido de un objeto de cadena no se puede modificar una vez creado el objeto, aunque la sintaxis parezca indicar que se puede hacer.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="3ca7e-112">Por ejemplo, al escribir este código, el compilador crea en realidad otro objeto de cadena para almacenar la nueva secuencia de caracteres, y este nuevo objeto se asigna a b.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="3ca7e-113">La cadena "h" pasa a ser apta para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="3ca7e-114">El operador [] puede usarse para acceso de solo lectura a determinados caracteres de un objeto `string`:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="3ca7e-115">Los literales de cadena son del tipo `string` y se pueden escribir de dos formas, entre comillas y @-quoted.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="3ca7e-116">Los literales de cadena se incluyen entre comillas dobles ("):</span><span class="sxs-lookup"><span data-stu-id="3ca7e-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="3ca7e-117">Los literales de cadena pueden contener cualquier literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-117">String literals can contain any character literal.</span></span> <span data-ttu-id="3ca7e-118">Se incluyen secuencias de escape.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-118">Escape sequences are included.</span></span> <span data-ttu-id="3ca7e-119">En el ejemplo siguiente se usa una secuencia de escape `\\` para la barra diagonal inversa, `\u0066` para la letra f y `\n` para la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```csharp  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="3ca7e-120">El código de escape `\udddd` (donde `dddd` es un número de cuatro dígitos) representa el carácter Unicode U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="3ca7e-121">También se reconocen los códigos de escape Unicode de 8 dígitos: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="3ca7e-122">Los literales de cadena textual empiezan por `@` y también se incluyen entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="3ca7e-122">Verbatim string literals start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="3ca7e-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="3ca7e-124">La ventaja de las cadenas textuales es que las secuencias de escape *no* se procesan, lo que facilita la escritura de, por ejemplo, un nombre de archivo completo:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="3ca7e-125">Para incluir un signo de comillas dobles en una cadena @-quoted, duplíquelo:</span><span class="sxs-lookup"><span data-stu-id="3ca7e-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="3ca7e-126">Para saber qué otros usos tiene el carácter especial `@`, vea [@ -- identificador textual](../tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="3ca7e-126">For other uses of the `@` special character, see [@ -- verbatim identifier](../tokens/verbatim.md).</span></span>  
  
 <span data-ttu-id="3ca7e-127">Para obtener más información sobre las cadenas en C#, vea [Strings](../../../csharp/programming-guide/strings/index.md) (Cadenas [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="3ca7e-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ca7e-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ca7e-128">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="3ca7e-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3ca7e-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ca7e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca7e-130">See Also</span></span>  
 [<span data-ttu-id="3ca7e-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3ca7e-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3ca7e-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3ca7e-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3ca7e-133">Procedimientos recomendados para el uso de cadenas</span><span class="sxs-lookup"><span data-stu-id="3ca7e-133">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)  
 [<span data-ttu-id="3ca7e-134">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3ca7e-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="3ca7e-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3ca7e-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3ca7e-136">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="3ca7e-136">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="3ca7e-137">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="3ca7e-137">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="3ca7e-138">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="3ca7e-138">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="3ca7e-139">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="3ca7e-139">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="3ca7e-140">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="3ca7e-140">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)
