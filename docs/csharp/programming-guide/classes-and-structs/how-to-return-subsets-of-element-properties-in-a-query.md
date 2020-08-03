---
title: Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta - Guía de programación de C#
description: Aprenda a usar un tipo anónimo en una expresión de consulta de C# para devolver algunas de las propiedades de cada elemento de origen.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 882d94bc82527c14bd6c038f4bf574c2211b9089
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864376"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="045cf-103">Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="045cf-103">How to return subsets of element properties in a query (C# Programming Guide)</span></span>
<span data-ttu-id="045cf-104">Use un tipo anónimo en una expresión de consulta cuando se cumplan estas dos condiciones:</span><span class="sxs-lookup"><span data-stu-id="045cf-104">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="045cf-105">Solo quiere algunas de las propiedades de cada elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="045cf-105">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="045cf-106">No es necesario almacenar los resultados de la consulta fuera del ámbito del método en el que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="045cf-106">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="045cf-107">Si solo quiere devolver una propiedad o campo de cada elemento de origen, puede usar simplemente el operador de punto en la cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="045cf-107">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="045cf-108">Por ejemplo, para devolver solo el `ID` de cada `student`, escriba la cláusula `select` como sigue:</span><span class="sxs-lookup"><span data-stu-id="045cf-108">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="045cf-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="045cf-109">Example</span></span>  
 <span data-ttu-id="045cf-110">En el ejemplo siguiente se muestra cómo usar un tipo anónimo para devolver solo un subconjunto de las propiedades de cada elemento de origen que coincida con la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="045cf-110">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="045cf-111">Tenga en cuenta que, si no se especifica ningún nombre, el tipo anónimo usa los nombres del elemento de origen para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="045cf-111">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="045cf-112">Para asignar nombres nuevos a las propiedades del tipo anónimo, escriba la instrucción `select` como sigue:</span><span class="sxs-lookup"><span data-stu-id="045cf-112">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="045cf-113">Si lo intenta en el ejemplo anterior, también debe cambiar la instrucción `Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="045cf-113">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="045cf-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="045cf-114">Compiling the Code</span></span>  
  
<span data-ttu-id="045cf-115">Para ejecutar este código, copie y pegue la clase en una aplicación de consola de C# con una directiva `using` de System.Linq.</span><span class="sxs-lookup"><span data-stu-id="045cf-115">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="045cf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="045cf-116">See also</span></span>

- [<span data-ttu-id="045cf-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="045cf-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="045cf-118">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="045cf-118">Anonymous Types</span></span>](./anonymous-types.md)
- [<span data-ttu-id="045cf-119">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="045cf-119">LINQ in C#</span></span>](../../linq/index.md)
