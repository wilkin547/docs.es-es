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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1455ce7c3b07809d1dead8e98019c991475eb02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442152"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="96ad0-102">puntero a la función WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="96ad0-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="96ad0-103">Señala a una función que notifica al host que controlar una espera (<xref:System.Threading.WaitHandle>) se ha señalado o agotó el tiempo.</span><span class="sxs-lookup"><span data-stu-id="96ad0-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="96ad0-104">Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96ad0-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96ad0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96ad0-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96ad0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96ad0-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="96ad0-107">[in] Un puntero a un objeto que contiene información definida por el host.</span><span class="sxs-lookup"><span data-stu-id="96ad0-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="96ad0-108">[in] `true` si el identificador de espera agotado, o `false` si se envía una señal.</span><span class="sxs-lookup"><span data-stu-id="96ad0-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96ad0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96ad0-109">Remarks</span></span>  
 <span data-ttu-id="96ad0-110">La función a la que `WAITORTIMERCALLBACK` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="96ad0-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96ad0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96ad0-111">Requirements</span></span>  
 <span data-ttu-id="96ad0-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96ad0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96ad0-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96ad0-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96ad0-114">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="96ad0-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="96ad0-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96ad0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ad0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="96ad0-116">See Also</span></span>  
 [<span data-ttu-id="96ad0-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="96ad0-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
