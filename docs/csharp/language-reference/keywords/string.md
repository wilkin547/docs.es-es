---
title: string (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56847aad4cb8b0427594a299df2306d21675506b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="string-c-reference"></a><span data-ttu-id="089e7-102">string (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="089e7-102">string (C# Reference)</span></span>
<span data-ttu-id="089e7-103">El tipo `string` representa una secuencia de cero o más caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="089e7-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="089e7-104">`string` es un alias de <xref:System.String> en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="089e7-104">`string` is an alias for <xref:System.String> in the .NET Framework.</span></span>  
  
 <span data-ttu-id="089e7-105">Aunque `string` es un tipo de referencia, se definen los operadores de igualdad (`==` y `!=`) para comparar los valores de los objetos `string`, no las referencias.</span><span class="sxs-lookup"><span data-stu-id="089e7-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="089e7-106">Esto hace que las pruebas de igualdad entre cadenas sean más intuitivas.</span><span class="sxs-lookup"><span data-stu-id="089e7-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="089e7-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="089e7-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="089e7-108">Se muestra "True" y luego "False" porque el contenido de las cadenas es equivalente, pero `a` y `b` no hacen referencia a la misma instancia de cadena.</span><span class="sxs-lookup"><span data-stu-id="089e7-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="089e7-109">El operador + concatena cadenas:</span><span class="sxs-lookup"><span data-stu-id="089e7-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="089e7-110">Crea un objeto de cadena que contiene "good morning".</span><span class="sxs-lookup"><span data-stu-id="089e7-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="089e7-111">Las cadenas son *inmutables*: el contenido de un objeto de cadena no se puede modificar una vez creado el objeto, aunque la sintaxis parezca indicar que se puede hacer.</span><span class="sxs-lookup"><span data-stu-id="089e7-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="089e7-112">Por ejemplo, al escribir este código, el compilador crea en realidad otro objeto de cadena para almacenar la nueva secuencia de caracteres, y este nuevo objeto se asigna a b.</span><span class="sxs-lookup"><span data-stu-id="089e7-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="089e7-113">La cadena "h" pasa a ser apta para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="089e7-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="089e7-114">El operador [] puede usarse para acceso de solo lectura a determinados caracteres de un objeto `string`:</span><span class="sxs-lookup"><span data-stu-id="089e7-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="089e7-115">Los literales de cadena son del tipo `string` y se pueden escribir de dos formas, entre comillas y @-quoted.</span><span class="sxs-lookup"><span data-stu-id="089e7-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="089e7-116">Los literales de cadena se incluyen entre comillas dobles ("):</span><span class="sxs-lookup"><span data-stu-id="089e7-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="089e7-117">Los literales de cadena pueden contener cualquier literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="089e7-117">String literals can contain any character literal.</span></span> <span data-ttu-id="089e7-118">Se incluyen secuencias de escape.</span><span class="sxs-lookup"><span data-stu-id="089e7-118">Escape sequences are included.</span></span> <span data-ttu-id="089e7-119">En el ejemplo siguiente se usa una secuencia de escape `\\` para la barra diagonal inversa, `\u0066` para la letra f y `\n` para la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="089e7-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="089e7-120">El código de escape `\udddd` (donde `dddd` es un número de cuatro dígitos) representa el carácter Unicode U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="089e7-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="089e7-121">También se reconocen los códigos de escape Unicode de 8 dígitos: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="089e7-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="089e7-122">Los literales de cadena textual empiezan por @ y también se incluyen entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="089e7-122">Verbatim string literals start with @ and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="089e7-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="089e7-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="089e7-124">La ventaja de las cadenas textuales es que las secuencias de escape *no* se procesan, lo que facilita la escritura de, por ejemplo, un nombre de archivo completo:</span><span class="sxs-lookup"><span data-stu-id="089e7-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="089e7-125">Para incluir un signo de comillas dobles en una cadena @-quoted, duplíquelo:</span><span class="sxs-lookup"><span data-stu-id="089e7-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="089e7-126">Otro uso del símbolo @ se da con identificadores con referencia ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) que son palabras clave de C#.</span><span class="sxs-lookup"><span data-stu-id="089e7-126">Another use of the @ symbol is to use referenced ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) identifiers that are C# keywords.</span></span>  
  
 <span data-ttu-id="089e7-127">Para obtener más información sobre las cadenas en C#, vea [Strings](../../../csharp/programming-guide/strings/index.md) (Cadenas [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="089e7-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="089e7-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="089e7-128">Example</span></span>  
 <span data-ttu-id="089e7-129">[!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="089e7-129">[!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="089e7-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="089e7-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="089e7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="089e7-131">See Also</span></span>  
 <span data-ttu-id="089e7-132">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="089e7-133">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="089e7-134">[Procedimientos recomendados para el uso de cadenas en .NET Framework](../../../standard/base-types/best-practices-strings.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-134">[Best Practices for Using Strings](../../../standard/base-types/best-practices-strings.md) </span></span>  
 <span data-ttu-id="089e7-135">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-135">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="089e7-136">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="089e7-137">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md)  (Tipos de referencia [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="089e7-137">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="089e7-138">[Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="089e7-138">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="089e7-139">[Operaciones básicas de cadenas](../../../standard/base-types/basic-string-operations.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-139">[Basic String Operations](../../../standard/base-types/basic-string-operations.md) </span></span>  
 <span data-ttu-id="089e7-140">[Creación de nuevas cadenas](../../../standard/base-types/creating-new.md) </span><span class="sxs-lookup"><span data-stu-id="089e7-140">[Creating New Strings](../../../standard/base-types/creating-new.md) </span></span>  
 [<span data-ttu-id="089e7-141">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="089e7-141">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)

