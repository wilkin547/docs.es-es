---
title: ICorConfiguration::AddDebuggerSpecialThread (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b940c0dbe9462dda513e933b7360ff55a9b447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437354"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="33b5c-102">ICorConfiguration::AddDebuggerSpecialThread (Método)</span><span class="sxs-lookup"><span data-stu-id="33b5c-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="33b5c-103">Indica a los servicios de depuración que se debe permitir un subproceso determinado continúe ejecutándose mientras el depurador tiene una aplicación detenida en escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="33b5c-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33b5c-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33b5c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33b5c-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="33b5c-106">[in] El identificador del subproceso que debe permitir que continúe ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="33b5c-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33b5c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33b5c-107">Remarks</span></span>  
 <span data-ttu-id="33b5c-108">El subproceso especificado no se podrá ejecutar código administrado o escriba el tiempo de ejecución de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="33b5c-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="33b5c-109">Un ejemplo de un subproceso sería un subproceso en curso para admitir los depuradores de secuencia de comandos heredados.</span><span class="sxs-lookup"><span data-stu-id="33b5c-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b5c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33b5c-110">Requirements</span></span>  
 <span data-ttu-id="33b5c-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33b5c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33b5c-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33b5c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33b5c-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33b5c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33b5c-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33b5c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b5c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b5c-115">See Also</span></span>  
 [<span data-ttu-id="33b5c-116">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33b5c-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
