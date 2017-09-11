---
title: "Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
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
ms.openlocfilehash: 808a74f75e4dcbcec47735d98063138e2c7456e5
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="1b840-102">Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1b840-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="1b840-103">En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.</span><span class="sxs-lookup"><span data-stu-id="1b840-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="1b840-104">En este ejemplo se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`.</span><span class="sxs-lookup"><span data-stu-id="1b840-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="1b840-105">La instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="1b840-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="1b840-106">Esto *ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1b840-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="1b840-107">Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`.</span><span class="sxs-lookup"><span data-stu-id="1b840-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="1b840-108">Dado que el método `Copy` en este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador **/unsafe**.</span><span class="sxs-lookup"><span data-stu-id="1b840-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="1b840-109">Para establecer la opción en Visual Studio, haga clic con el botón derecho en el nombre del proyecto y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1b840-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="1b840-110">En la pestaña **Compilar**, seleccione **Permitir código no seguro**.</span><span class="sxs-lookup"><span data-stu-id="1b840-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b840-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b840-111">Example</span></span>  
 <span data-ttu-id="1b840-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b840-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span></span>  
  
 <span data-ttu-id="1b840-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1b840-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b840-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b840-114">See Also</span></span>  
 <span data-ttu-id="1b840-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b840-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1b840-116">[Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b840-116">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="1b840-117">[/unsafe (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="1b840-117">[/unsafe (C# Compiler Options)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span></span>  
 [<span data-ttu-id="1b840-118">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="1b840-118">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

