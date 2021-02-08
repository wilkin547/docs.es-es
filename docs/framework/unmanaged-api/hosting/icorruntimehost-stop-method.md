---
description: 'Más información sobre: ICorRuntimeHost:: STOP (método)'
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
ms.openlocfilehash: b44c77b7d0fe3a078efa11756f5fac7ba400ca5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789598"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="e99ad-103">ICorRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="e99ad-103">ICorRuntimeHost::Stop Method</span></span>

<span data-ttu-id="e99ad-104">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="e99ad-104">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e99ad-105">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e99ad-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e99ad-106">Return Value</span></span>  
  
|<span data-ttu-id="e99ad-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e99ad-107">HRESULT</span></span>|<span data-ttu-id="e99ad-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e99ad-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e99ad-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e99ad-109">S_OK</span></span>|<span data-ttu-id="e99ad-110">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e99ad-110">The operation was successful.</span></span>|  
|<span data-ttu-id="e99ad-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e99ad-111">S_FALSE</span></span>|<span data-ttu-id="e99ad-112">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="e99ad-112">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e99ad-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e99ad-113">E_FAIL</span></span>|<span data-ttu-id="e99ad-114">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e99ad-114">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e99ad-115">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e99ad-115">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e99ad-116">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e99ad-116">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e99ad-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e99ad-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e99ad-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e99ad-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e99ad-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e99ad-119">Remarks</span></span>  

 <span data-ttu-id="e99ad-120">Normalmente no es necesario llamar al `Stop` método, porque el código deja de ejecutarse cuando finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="e99ad-120">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e99ad-121">Después de una llamada a `Stop` , CLR no se puede reinicializar en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="e99ad-121">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e99ad-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e99ad-122">Requirements</span></span>  

 <span data-ttu-id="e99ad-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e99ad-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e99ad-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e99ad-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e99ad-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e99ad-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e99ad-126">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e99ad-126">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99ad-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e99ad-127">See also</span></span>

- [<span data-ttu-id="e99ad-128">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e99ad-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
