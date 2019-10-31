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
ms.openlocfilehash: db6a20dee21b6c8bbd55fa9b52a159a00fe310d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092038"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="f75f0-102">puntero a la función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="f75f0-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="f75f0-103">Señala a una función que notifica al host que un identificador de espera (<xref:System.Threading.WaitHandle>) se ha señalado o ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f75f0-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="f75f0-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f75f0-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f75f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f75f0-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f75f0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f75f0-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="f75f0-107">de Un puntero a un objeto que contiene información definida por el host.</span><span class="sxs-lookup"><span data-stu-id="f75f0-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="f75f0-108">[in] `true` si el identificador de espera ha agotado el tiempo de espera o `false` si se ha señalado.</span><span class="sxs-lookup"><span data-stu-id="f75f0-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f75f0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f75f0-109">Remarks</span></span>  
 <span data-ttu-id="f75f0-110">Función a la que `WAITORTIMERCALLBACK` puntos es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="f75f0-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f75f0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f75f0-111">Requirements</span></span>  
 <span data-ttu-id="f75f0-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f75f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f75f0-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f75f0-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f75f0-114">**Biblioteca:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="f75f0-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f75f0-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f75f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75f0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f75f0-116">See also</span></span>

- [<span data-ttu-id="f75f0-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f75f0-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
