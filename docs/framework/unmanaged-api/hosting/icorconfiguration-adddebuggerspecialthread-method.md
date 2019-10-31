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
ms.openlocfilehash: c5d6cfa3826667514eb70f9bb0df118d9ba0d07c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127818"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="91322-102">ICorConfiguration::AddDebuggerSpecialThread (Método)</span><span class="sxs-lookup"><span data-stu-id="91322-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="91322-103">Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="91322-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91322-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91322-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91322-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91322-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="91322-106">de IDENTIFICADOR del subproceso al que se debe permitir que continúe la ejecución.</span><span class="sxs-lookup"><span data-stu-id="91322-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91322-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91322-107">Remarks</span></span>  
 <span data-ttu-id="91322-108">El subproceso especificado no podrá ejecutar código administrado ni entrar en el tiempo de ejecución de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="91322-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="91322-109">Un ejemplo de este tipo de subproceso sería un subproceso en proceso para admitir depuradores de script heredados.</span><span class="sxs-lookup"><span data-stu-id="91322-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91322-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91322-110">Requirements</span></span>  
 <span data-ttu-id="91322-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91322-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91322-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="91322-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91322-113">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="91322-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91322-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91322-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91322-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="91322-115">See also</span></span>

- [<span data-ttu-id="91322-116">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91322-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
