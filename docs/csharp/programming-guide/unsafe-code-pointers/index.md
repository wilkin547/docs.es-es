---
title: 'Código no seguro y punteros: guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 013af4e55c8fc396bbc92058d7fb454484f3263e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711836"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="7f0f9-102">Código no seguro y punteros (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7f0f9-102">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="7f0f9-103">Para mantener la seguridad de tipos, C# no admite la aritmética de puntero de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="7f0f9-104">En cambio, mediante el uso de la palabra clave [unsafe](../../language-reference/keywords/unsafe.md), puede definir un contexto no seguro en el que se pueden usar punteros.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-104">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="7f0f9-105">Para más información sobre los punteros, vea [Tipos de puntero](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f0f9-105">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f0f9-106">En Common Language Runtime (CLR), el código no seguro se conoce como código no comprobable.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="7f0f9-107">El código no seguro en C# no es necesariamente peligroso; solo es código cuya seguridad no puede comprobar CLR.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="7f0f9-108">Por lo tanto, CLR solo ejecutará código no seguro si se encuentra en un ensamblado de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="7f0f9-109">Si usa código no seguro, es su responsabilidad asegurarse de que el código no presenta riesgos de seguridad o errores de puntero.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="7f0f9-110">Introducción sobre el código no seguro</span><span class="sxs-lookup"><span data-stu-id="7f0f9-110">Unsafe code overview</span></span>

<span data-ttu-id="7f0f9-111">El código no seguro tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f0f9-111">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="7f0f9-112">Los métodos, tipos y bloques de código se pueden definir como no seguros.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-112">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="7f0f9-113">En algunos casos, el código no seguro puede aumentar el rendimiento de la aplicación al eliminar las comprobaciones de límites de matriz.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="7f0f9-114">El código no seguro es necesario al llamar a funciones nativas que requieren punteros.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-114">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="7f0f9-115">El código no seguro presenta riesgos para la seguridad y la estabilidad.</span><span class="sxs-lookup"><span data-stu-id="7f0f9-115">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="7f0f9-116">El código que contiene bloques no seguros debe compilarse con la opción del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7f0f9-116">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="7f0f9-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7f0f9-117">Related sections</span></span>

<span data-ttu-id="7f0f9-118">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="7f0f9-118">For more information, see:</span></span>

- [<span data-ttu-id="7f0f9-119">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="7f0f9-119">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="7f0f9-120">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="7f0f9-120">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="7f0f9-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7f0f9-121">C# language specification</span></span>

<span data-ttu-id="7f0f9-122">Para más información, vea el tema sobre [código no seguro](~/_csharplang/spec/unsafe-code.md) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7f0f9-122">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f0f9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f0f9-123">See also</span></span>

- [<span data-ttu-id="7f0f9-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7f0f9-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7f0f9-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="7f0f9-125">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
