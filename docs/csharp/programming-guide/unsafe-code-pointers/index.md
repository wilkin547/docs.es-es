---
title: Código no seguro y punteros (Guía de programación de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32856461fbc6513509342a3567240de723f1fe8f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="3f7fe-102">Código no seguro y punteros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3f7fe-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="3f7fe-103">Para mantener la seguridad de tipos, C# no admite la aritmética de puntero de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="3f7fe-104">En cambio, mediante el uso de la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), puede definir un contexto no seguro en el que se pueden usar punteros.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="3f7fe-105">Para obtener más información sobre los punteros, vea [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="3f7fe-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f7fe-106">En Common Language Runtime (CLR), el código no seguro se conoce como código no comprobable.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="3f7fe-107">El código no seguro en C# no es necesariamente peligroso; solo es código cuya seguridad no puede comprobar CLR.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="3f7fe-108">Por lo tanto, CLR solo ejecutará código no seguro si se encuentra en un ensamblado de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="3f7fe-109">Si usa código no seguro, es su responsabilidad asegurarse de que el código no presenta riesgos de seguridad o errores de puntero.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="3f7fe-110">Información general sobre el código no seguro</span><span class="sxs-lookup"><span data-stu-id="3f7fe-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="3f7fe-111">El código no seguro tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f7fe-111">Unsafe code has the following properties:</span></span>  
  
-   <span data-ttu-id="3f7fe-112">Los métodos, tipos y bloques de código se pueden definir como no seguros.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
-   <span data-ttu-id="3f7fe-113">En algunos casos, el código no seguro puede aumentar el rendimiento de la aplicación al eliminar las comprobaciones de límites de matriz.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
-   <span data-ttu-id="3f7fe-114">El código no seguro es necesario al llamar a funciones nativas que requieren punteros.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
-   <span data-ttu-id="3f7fe-115">El código no seguro presenta riesgos para la seguridad y la estabilidad.</span><span class="sxs-lookup"><span data-stu-id="3f7fe-115">Using unsafe code introduces security and stability risks.</span></span>  
  
-   <span data-ttu-id="3f7fe-116">Para que C# compile código no seguro, la aplicación debe compilarse con [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3f7fe-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3f7fe-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3f7fe-117">Related Sections</span></span>  
 <span data-ttu-id="3f7fe-118">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="3f7fe-118">For more information, see:</span></span>  
  
-   [<span data-ttu-id="3f7fe-119">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="3f7fe-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [<span data-ttu-id="3f7fe-120">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="3f7fe-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [<span data-ttu-id="3f7fe-121">Cómo: Utilizar punteros para copiar una matriz de bytes</span><span class="sxs-lookup"><span data-stu-id="3f7fe-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [<span data-ttu-id="3f7fe-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="3f7fe-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="3f7fe-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3f7fe-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f7fe-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f7fe-124">See Also</span></span>  
 [<span data-ttu-id="3f7fe-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3f7fe-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
