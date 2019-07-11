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
ms.openlocfilehash: a73232fb9327880f0038097d71698ddf8bf005e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779899"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="b4535-102">ICorConfiguration::AddDebuggerSpecialThread (Método)</span><span class="sxs-lookup"><span data-stu-id="b4535-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="b4535-103">Indica a los servicios de depuración que un subproceso en particular debe permitirse seguirse ejecutando mientras el depurador tiene una aplicación detenida en escenarios de depuración administrados o no administrado.</span><span class="sxs-lookup"><span data-stu-id="b4535-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4535-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4535-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4535-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4535-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="b4535-106">[in] El identificador del subproceso que se debe permitir que continúe ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="b4535-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4535-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4535-107">Remarks</span></span>  
 <span data-ttu-id="b4535-108">El subproceso especificado no se permitirá ejecutar código administrado o escriba el tiempo de ejecución de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="b4535-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="b4535-109">Un ejemplo de un subproceso de este tipo sería un subproceso en curso para admitir los depuradores de secuencia de comandos heredados.</span><span class="sxs-lookup"><span data-stu-id="b4535-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4535-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4535-110">Requirements</span></span>  
 <span data-ttu-id="b4535-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4535-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4535-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4535-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4535-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4535-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4535-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4535-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4535-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4535-115">See also</span></span>

- [<span data-ttu-id="b4535-116">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4535-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
