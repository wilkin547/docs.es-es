---
title: Reglas de portabilidad y de interoperabilidad (análisis de código)
description: Más información sobre la portabilidad de reglas de análisis de código y las reglas de interoperabilidad
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.Portablityrules
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis rules, interoperability rules, portability rules
- portability rules
- warnings, portability
- interoperability rules
- warnings, interoperability
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a20cd77e13c4a8b95633d129990667f0a8de3ee8
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592409"
---
# <a name="portability-and-interoperability-rules"></a><span data-ttu-id="d288d-103">Reglas de portabilidad e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d288d-103">Portability and interoperability rules</span></span>

<span data-ttu-id="d288d-104">Las reglas de portabilidad admiten la portabilidad en diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="d288d-104">Portability rules support portability across different platforms.</span></span> <span data-ttu-id="d288d-105">Las reglas de interoperabilidad admiten la interacción con clientes COM.</span><span class="sxs-lookup"><span data-stu-id="d288d-105">Interoperability rules support interaction with COM clients.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d288d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d288d-106">In this section</span></span>

| <span data-ttu-id="d288d-107">Regla</span><span class="sxs-lookup"><span data-stu-id="d288d-107">Rule</span></span> | <span data-ttu-id="d288d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d288d-108">Description</span></span> |
| - | - |
| [<span data-ttu-id="d288d-109">CA1401: P/Invoke no debe estar visible</span><span class="sxs-lookup"><span data-stu-id="d288d-109">CA1401: P/Invokes should not be visible</span></span>](ca1401.md) | <span data-ttu-id="d288d-110">Un método público o protegido en un tipo público tiene el System.Runtime.InteropServices.Dllatributo ImportAttribute (también se implementa mediante la palabra clave declare en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d288d-110">A public or protected method in a public type has the System.Runtime.InteropServices.DllImportAttribute attribute (also implemented by the Declare keyword in Visual Basic).</span></span> <span data-ttu-id="d288d-111">No se deberían exponer estos métodos.</span><span class="sxs-lookup"><span data-stu-id="d288d-111">Such methods should not be exposed.</span></span> |
| [<span data-ttu-id="d288d-112">CA1416: Validación de la compatibilidad con las plataformas</span><span class="sxs-lookup"><span data-stu-id="d288d-112">CA1416: Validate platform compatibility</span></span>](ca1416.md) | <span data-ttu-id="d288d-113">El uso de API dependientes de la plataforma en un componente hace que el código deje de funcionar en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="d288d-113">Using platform-dependent APIs on a component makes the code no longer work across all platforms.</span></span> |
| [<span data-ttu-id="d288d-114">CA1417: no se usa `OutAttribute` en parámetros de cadena para P/Invoke</span><span class="sxs-lookup"><span data-stu-id="d288d-114">CA1417: Do not use `OutAttribute` on string parameters for P/Invokes</span></span>](ca1417.md) | <span data-ttu-id="d288d-115">Los parámetros de cadena pasados por valor con el `OutAttribute` pueden desestabilizar el tiempo de ejecución si la cadena es una cadena interna.</span><span class="sxs-lookup"><span data-stu-id="d288d-115">String parameters passed by value with the `OutAttribute` can destabilize the runtime if the string is an interned string.</span></span> |
