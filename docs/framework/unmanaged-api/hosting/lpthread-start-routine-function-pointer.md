---
title: "puntero a la función LPTHREAD_START_ROUTINE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPTHREAD_START_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPTHREAD_START_ROUTINE
helpviewer_keywords: LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d28cdbfa2cb6c2c1f6b730e34b623a621119bc3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="534f7-102">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="534f7-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="534f7-103">Señala a una función que notifica al host que ha empezado a ejecutar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="534f7-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="534f7-104">Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="534f7-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="534f7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="534f7-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="534f7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="534f7-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="534f7-107">[in] Un puntero al código que ha iniciado la ejecución.</span><span class="sxs-lookup"><span data-stu-id="534f7-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="534f7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="534f7-108">Remarks</span></span>  
 <span data-ttu-id="534f7-109">La función a la que `LPTHREAD_START_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="534f7-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="534f7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="534f7-110">Requirements</span></span>  
 <span data-ttu-id="534f7-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="534f7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534f7-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="534f7-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="534f7-113">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="534f7-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="534f7-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="534f7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534f7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="534f7-115">See Also</span></span>  
 [<span data-ttu-id="534f7-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="534f7-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
