---
description: 'Más información sobre: ICorConfiguration:: Adddebuggerspecialthread ((método)'
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
ms.openlocfilehash: b6904c2e4d5c265244ac096e0d64c2fc7f5d1be5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636720"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="93980-103">ICorConfiguration::AddDebuggerSpecialThread (Método)</span><span class="sxs-lookup"><span data-stu-id="93980-103">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>

<span data-ttu-id="93980-104">Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="93980-104">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93980-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93980-105">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93980-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93980-106">Parameters</span></span>  

 `dwSpecialThreadId`  
 <span data-ttu-id="93980-107">de IDENTIFICADOR del subproceso al que se debe permitir que continúe la ejecución.</span><span class="sxs-lookup"><span data-stu-id="93980-107">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93980-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="93980-108">Remarks</span></span>  

 <span data-ttu-id="93980-109">El subproceso especificado no podrá ejecutar código administrado ni entrar en el tiempo de ejecución de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="93980-109">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="93980-110">Un ejemplo de este tipo de subproceso sería un subproceso en proceso para admitir depuradores de script heredados.</span><span class="sxs-lookup"><span data-stu-id="93980-110">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93980-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93980-111">Requirements</span></span>  

 <span data-ttu-id="93980-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93980-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93980-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="93980-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93980-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93980-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93980-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93980-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93980-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="93980-116">See also</span></span>

- [<span data-ttu-id="93980-117">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93980-117">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
