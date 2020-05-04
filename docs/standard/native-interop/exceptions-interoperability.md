---
title: Interoperabilidad de excepciones
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794619"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="5dcab-102">Trabajo con excepciones de interoperabilidad en código no administrado</span><span class="sxs-lookup"><span data-stu-id="5dcab-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="5dcab-103">La interoperabilidad de excepciones de código no administrado solo se admite en plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="5dcab-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="5dcab-104">En las plataformas que no son Windows surgen problemas de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="5dcab-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="5dcab-105">Dado que ABI de UNIX no tiene ninguna definición para el control de excepciones, el código administrado no puede saber cómo funcionan las entrañas de los mecanismos de excepción</span><span class="sxs-lookup"><span data-stu-id="5dcab-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="5dcab-106">y, por lo tanto, las excepciones pueden acabar dando lugar a comportamientos imprevisibles y bloqueos.</span><span class="sxs-lookup"><span data-stu-id="5dcab-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="5dcab-107">Comportamientos de setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="5dcab-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="5dcab-108">La interoperabilidad con funciones de C `setjmp` y `longjmp` no es posible.</span><span class="sxs-lookup"><span data-stu-id="5dcab-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="5dcab-109">No se puede usar `longjmp` para omitir los marcos administrados.</span><span class="sxs-lookup"><span data-stu-id="5dcab-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="5dcab-110">Para más información, vea la [documentación de longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="5dcab-110">For more information, see [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dcab-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dcab-111">See also</span></span>

- [<span data-ttu-id="5dcab-112">Excepciones</span><span class="sxs-lookup"><span data-stu-id="5dcab-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="5dcab-113">Interoperabilidad con bibliotecas nativas</span><span class="sxs-lookup"><span data-stu-id="5dcab-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
