---
title: Interoperabilidad de excepciones
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830628"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="04d81-102">Trabajo con excepciones de interoperabilidad en código no administrado</span><span class="sxs-lookup"><span data-stu-id="04d81-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="04d81-103">La interoperabilidad de excepciones de código no administrado solo se admite en plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="04d81-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="04d81-104">En las plataformas que no son Windows surgen problemas de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="04d81-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="04d81-105">Dado que ABI de UNIX no tiene ninguna definición para el control de excepciones, el código administrado no puede saber cómo funcionan las entrañas de los mecanismos de excepción</span><span class="sxs-lookup"><span data-stu-id="04d81-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="04d81-106">y, por lo tanto, las excepciones pueden acabar dando lugar a comportamientos imprevisibles y bloqueos.</span><span class="sxs-lookup"><span data-stu-id="04d81-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="04d81-107">Comportamientos de setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="04d81-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="04d81-108">La interoperabilidad con funciones de C `setjmp` y `longjmp` no es posible.</span><span class="sxs-lookup"><span data-stu-id="04d81-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="04d81-109">No se puede usar `longjmp` para omitir los marcos administrados.</span><span class="sxs-lookup"><span data-stu-id="04d81-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="04d81-110">Para más información, vea la [documentación de longjmp](/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="04d81-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="04d81-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="04d81-111">See also</span></span>

- [<span data-ttu-id="04d81-112">Excepciones</span><span class="sxs-lookup"><span data-stu-id="04d81-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="04d81-113">Interoperabilidad con bibliotecas nativas</span><span class="sxs-lookup"><span data-stu-id="04d81-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
