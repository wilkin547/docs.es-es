---
title: Exception. PrepForRemoting (método) (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214896"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="ba00b-102">Método Exception.PrepForRemoting</span><span class="sxs-lookup"><span data-stu-id="ba00b-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="ba00b-103">Conserva el seguimiento de la pila del servidor al anexarlo al mensaje antes de que se vuelva a producir la excepción en el sitio de llamada de cliente.</span><span class="sxs-lookup"><span data-stu-id="ba00b-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="ba00b-104">Devuelve</span><span class="sxs-lookup"><span data-stu-id="ba00b-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="ba00b-105">Esta instancia de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="ba00b-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba00b-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba00b-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ba00b-107">El método `Exception.PrepForRemoting` es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="ba00b-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ba00b-108">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="ba00b-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba00b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba00b-109">Requirements</span></span>

<span data-ttu-id="ba00b-110">**Espacio de nombres:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="ba00b-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="ba00b-111">**Ensamblado:** mscorlib. dll (en mscorlib. dll)</span><span class="sxs-lookup"><span data-stu-id="ba00b-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="ba00b-112">**.NET Framework versiones:** Disponible desde 1,0.</span><span class="sxs-lookup"><span data-stu-id="ba00b-112">**.NET Framework versions:** Available since 1.0.</span></span>
