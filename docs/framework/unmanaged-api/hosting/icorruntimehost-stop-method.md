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
ms.openlocfilehash: b1af01559e65bd80fc62cb2eba44bf21d4fa3113
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770911"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="ef0fb-102">ICorRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="ef0fb-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="ef0fb-103">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef0fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef0fb-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ef0fb-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef0fb-105">Return Value</span></span>  
  
|<span data-ttu-id="ef0fb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef0fb-106">HRESULT</span></span>|<span data-ttu-id="ef0fb-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef0fb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef0fb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef0fb-108">S_OK</span></span>|<span data-ttu-id="ef0fb-109">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-109">The operation was successful.</span></span>|  
|<span data-ttu-id="ef0fb-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ef0fb-110">S_FALSE</span></span>|<span data-ttu-id="ef0fb-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ef0fb-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef0fb-112">E_FAIL</span></span>|<span data-ttu-id="ef0fb-113">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ef0fb-114">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ef0fb-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ef0fb-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef0fb-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef0fb-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef0fb-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef0fb-118">Remarks</span></span>  
 <span data-ttu-id="ef0fb-119">Normalmente no es necesario llamar a la `Stop` método, porque el código deja de ejecutarse cuando finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef0fb-120">Después de llamar a `Stop`, CLR no se pueden reinicializar en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="ef0fb-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef0fb-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef0fb-121">Requirements</span></span>  
 <span data-ttu-id="ef0fb-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef0fb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef0fb-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef0fb-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef0fb-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef0fb-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef0fb-125">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ef0fb-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0fb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef0fb-126">See also</span></span>

- [<span data-ttu-id="ef0fb-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef0fb-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
