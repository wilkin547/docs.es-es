---
title: using (Directiva, Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 180c038987e7de6b39a8eae0e86871eea41a40bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280096"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="839b3-102">using (Directiva, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="839b3-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="839b3-103">La directiva `using` tiene tres usos:</span><span class="sxs-lookup"><span data-stu-id="839b3-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="839b3-104">Permitir el uso de tipos en un espacio de nombres de manera que no tenga que calificar el uso de un tipo en dicho espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="839b3-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="839b3-105">Permitirle acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="839b3-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="839b3-106">Para obtener más información, vea [using static (Directiva)](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="839b3-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="839b3-107">Para crear un alias para un espacio de nombre o un tipo.</span><span class="sxs-lookup"><span data-stu-id="839b3-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="839b3-108">Esto se conoce como *alias using (Directiva)*.</span><span class="sxs-lookup"><span data-stu-id="839b3-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="839b3-109">La palabra clave `using` también se usa para crear *instrucciones using*, que ayudan a garantizar que los objetos <xref:System.IDisposable>, como archivos y fuentes, se tratan correctamente.</span><span class="sxs-lookup"><span data-stu-id="839b3-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="839b3-110">Consulte [using (Instrucción)](../../../csharp/language-reference/keywords/using-statement.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="839b3-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="839b3-111">Usar el tipo estático</span><span class="sxs-lookup"><span data-stu-id="839b3-111">Using Static Type</span></span>  
 <span data-ttu-id="839b3-112">Puede acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo:</span><span class="sxs-lookup"><span data-stu-id="839b3-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="839b3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="839b3-113">Remarks</span></span>  
 <span data-ttu-id="839b3-114">El ámbito de una directiva `using` se limita al archivo en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="839b3-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="839b3-115">Cree un alias `using` para facilitar la calificación de un identificador como espacio de nombres o tipo.</span><span class="sxs-lookup"><span data-stu-id="839b3-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="839b3-116">El lado derecho de una directiva de alias using siempre debe ser un tipo completo independientemente de las directivas using que lo precedan.</span><span class="sxs-lookup"><span data-stu-id="839b3-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="839b3-117">Cree una directiva `using` para usar los tipos de un espacio de nombres sin tener que especificarlo.</span><span class="sxs-lookup"><span data-stu-id="839b3-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="839b3-118">Una directiva `using` no proporciona acceso a los espacios de nombres que están anidados en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="839b3-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="839b3-119">Los espacios de nombres se dividen en dos categorías: definidos por el sistema y definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="839b3-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="839b3-120">Los espacios de nombres definidos por el usuario son espacios de nombres definidos en el código.</span><span class="sxs-lookup"><span data-stu-id="839b3-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="839b3-121">Para obtener una lista de los espacios de nombres definidos por el sistema, vea [Información general de la biblioteca de clases de .NET](../../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="839b3-121">For a list of the system-defined namespaces, see [.NET Framework Class Library Overview](../../../standard/class-library-overview.md).</span></span>  
  
 <span data-ttu-id="839b3-122">Para obtener ejemplos de cómo hacer referencia a métodos en otros ensamblados, vea [Crear y usar ensamblados desde la línea de comandos (C#)](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="839b3-122">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="839b3-123">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="839b3-123">Example 1</span></span>  
  
 <span data-ttu-id="839b3-124">En el ejemplo siguiente se muestra cómo definir y usar un alias `using` para un espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="839b3-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="839b3-125">Una directiva de alias using no puede tener un tipo genérico abierto en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="839b3-125">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="839b3-126">Por ejemplo, no puede crear un alias using para List\<T>, pero puede crear uno para List\<int>.</span><span class="sxs-lookup"><span data-stu-id="839b3-126">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="839b3-127">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="839b3-127">Example 2</span></span>  
  
 <span data-ttu-id="839b3-128">En el ejemplo siguiente se muestra cómo definir una directiva `using` y un alias `using` para una clase:</span><span class="sxs-lookup"><span data-stu-id="839b3-128">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="839b3-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="839b3-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="839b3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="839b3-130">See Also</span></span>  
 [<span data-ttu-id="839b3-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="839b3-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="839b3-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="839b3-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="839b3-133">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="839b3-133">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
 [<span data-ttu-id="839b3-134">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="839b3-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="839b3-135">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="839b3-135">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="839b3-136">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="839b3-136">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="839b3-137">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="839b3-137">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
