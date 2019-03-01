---
title: CorExitProcess (Función)
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e0afe278b22e54b326ef17dc416b4632a853eda
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212344"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="e86e5-102">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="e86e5-102">CorExitProcess Function</span></span>
<span data-ttu-id="e86e5-103">Se cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="e86e5-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="e86e5-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e86e5-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="e86e5-105">Use la [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e86e5-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e86e5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e86e5-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e86e5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e86e5-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="e86e5-108">Un entero que especifica el código de salida.</span><span class="sxs-lookup"><span data-stu-id="e86e5-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e86e5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e86e5-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e86e5-110">A partir del [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` se cierra cada runtime iniciado en el proceso, no solo el tiempo de ejecución a la que se han enlazado las API heredadas.</span><span class="sxs-lookup"><span data-stu-id="e86e5-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e86e5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e86e5-111">Requirements</span></span>  
 <span data-ttu-id="e86e5-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e86e5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e86e5-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e86e5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e86e5-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e86e5-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e86e5-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e86e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e86e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e86e5-116">See also</span></span>
- [<span data-ttu-id="e86e5-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e86e5-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
