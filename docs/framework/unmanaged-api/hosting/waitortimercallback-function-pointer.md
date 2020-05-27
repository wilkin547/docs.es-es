---
title: puntero a la función WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009459"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="e69aa-102">puntero a la función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="e69aa-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="e69aa-103">Señala a una función que notifica al host que un identificador de espera ( <xref:System.Threading.WaitHandle> ) se ha señalado o ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e69aa-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="e69aa-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e69aa-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e69aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e69aa-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e69aa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e69aa-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="e69aa-107">de Un puntero a un objeto que contiene información definida por el host.</span><span class="sxs-lookup"><span data-stu-id="e69aa-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="e69aa-108">[in] `true` Si el identificador de espera ha agotado el tiempo de espera, o `false` si se ha señalado.</span><span class="sxs-lookup"><span data-stu-id="e69aa-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e69aa-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e69aa-109">Remarks</span></span>  
 <span data-ttu-id="e69aa-110">La función a la que `WAITORTIMERCALLBACK` apunta es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="e69aa-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e69aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e69aa-111">Requirements</span></span>  
 <span data-ttu-id="e69aa-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e69aa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e69aa-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e69aa-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e69aa-114">**Biblioteca:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="e69aa-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e69aa-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e69aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69aa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e69aa-116">See also</span></span>

- [<span data-ttu-id="e69aa-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e69aa-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
