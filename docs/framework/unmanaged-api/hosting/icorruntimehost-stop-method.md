---
title: ICorRuntimeHost::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca51b87e7afc8e9e48d541a32b3bd60a19a5ff70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965965"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="6006d-102">ICorRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="6006d-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="6006d-103">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="6006d-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6006d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6006d-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6006d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6006d-105">Return Value</span></span>  
  
|<span data-ttu-id="6006d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6006d-106">HRESULT</span></span>|<span data-ttu-id="6006d-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6006d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6006d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6006d-108">S_OK</span></span>|<span data-ttu-id="6006d-109">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6006d-109">The operation was successful.</span></span>|  
|<span data-ttu-id="6006d-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6006d-110">S_FALSE</span></span>|<span data-ttu-id="6006d-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="6006d-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6006d-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6006d-112">E_FAIL</span></span>|<span data-ttu-id="6006d-113">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6006d-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6006d-114">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6006d-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6006d-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6006d-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6006d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6006d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6006d-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6006d-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6006d-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6006d-118">Remarks</span></span>  
 <span data-ttu-id="6006d-119">Normalmente no es necesario llamar `Stop` al método, porque el código deja de ejecutarse cuando finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="6006d-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6006d-120">Después de una llamada `Stop`a, CLR no se puede reinicializar en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="6006d-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6006d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6006d-121">Requirements</span></span>  
 <span data-ttu-id="6006d-122">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6006d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6006d-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6006d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6006d-124">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6006d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6006d-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="6006d-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6006d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6006d-126">See also</span></span>

- [<span data-ttu-id="6006d-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6006d-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
