---
title: typeof (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.openlocfilehash: fdb335e44a5a3634520d3a86495a4508597b4f70
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="typeof-c-reference"></a><span data-ttu-id="910b2-102">typeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="910b2-102">typeof (C# Reference)</span></span>
<span data-ttu-id="910b2-103">Se usa para obtener el objeto `System.Type` de un tipo.</span><span class="sxs-lookup"><span data-stu-id="910b2-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="910b2-104">Una expresión `typeof` tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="910b2-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="910b2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="910b2-105">Remarks</span></span>  
 <span data-ttu-id="910b2-106">Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="910b2-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="910b2-107">El operador `typeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="910b2-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="910b2-108">El operador `typeof` también puede usarse en tipos genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="910b2-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="910b2-109">Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación.</span><span class="sxs-lookup"><span data-stu-id="910b2-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="910b2-110">En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico.</span><span class="sxs-lookup"><span data-stu-id="910b2-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="910b2-111">Suponga que el método es una instancia de un tipo de MethodInfo:</span><span class="sxs-lookup"><span data-stu-id="910b2-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="910b2-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="910b2-112">Example</span></span>  
 <span data-ttu-id="910b2-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="910b2-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="910b2-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="910b2-114">Example</span></span>  
 <span data-ttu-id="910b2-115">En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico.</span><span class="sxs-lookup"><span data-stu-id="910b2-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="910b2-116">Esto varía en función de los requisitos de almacenamiento del número resultante.</span><span class="sxs-lookup"><span data-stu-id="910b2-116">This depends on the storage requirements of the resulting number.</span></span>  
  
 <span data-ttu-id="910b2-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="910b2-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="910b2-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="910b2-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="910b2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="910b2-119">See Also</span></span>  
 <span data-ttu-id="910b2-120"><xref:System.Type?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="910b2-120"><xref:System.Type?displayProperty=fullName></span></span>   
 <span data-ttu-id="910b2-121">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="910b2-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="910b2-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="910b2-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="910b2-123">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="910b2-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="910b2-124">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="910b2-124">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 [<span data-ttu-id="910b2-125">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="910b2-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

