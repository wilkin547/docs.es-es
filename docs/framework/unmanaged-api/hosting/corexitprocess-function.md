---
title: "CorExitProcess (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 560f63c131ad336a3ff4b4edec0aed2b58d33ba5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corexitprocess-function"></a><span data-ttu-id="c5e5f-102">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="c5e5f-102">CorExitProcess Function</span></span>
<span data-ttu-id="c5e5f-103">Se cierra el proceso actual no administrado.</span><span class="sxs-lookup"><span data-stu-id="c5e5f-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="c5e5f-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5e5f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c5e5f-105">Use la [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c5e5f-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5e5f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5e5f-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5e5f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5e5f-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="c5e5f-108">Un entero que especifica el código de salida de proceso.</span><span class="sxs-lookup"><span data-stu-id="c5e5f-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5e5f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5e5f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5e5f-110">A partir del [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` sale de cada runtime iniciado en el proceso, no solo el tiempo de ejecución a la que se han enlazado las API heredadas.</span><span class="sxs-lookup"><span data-stu-id="c5e5f-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5e5f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5e5f-111">Requirements</span></span>  
 <span data-ttu-id="c5e5f-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5e5f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5e5f-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5e5f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5e5f-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5e5f-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5e5f-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5e5f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e5f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5e5f-116">See Also</span></span>  
 [<span data-ttu-id="c5e5f-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c5e5f-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
