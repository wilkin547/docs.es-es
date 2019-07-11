---
title: ICLRErrorReportingManager::EndCustomDump (Método)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c2d2e5454a26111748f9676cfe1ce5caa76cad5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772840"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="85b30-102">ICLRErrorReportingManager::EndCustomDump (Método)</span><span class="sxs-lookup"><span data-stu-id="85b30-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="85b30-103">Quita la configuración de volcado de pila personalizada que se especificó en una llamada anterior a la [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="85b30-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85b30-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="85b30-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="85b30-105">Return Value</span></span>  
  
|<span data-ttu-id="85b30-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85b30-106">HRESULT</span></span>|<span data-ttu-id="85b30-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85b30-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85b30-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="85b30-108">S_OK</span></span>|<span data-ttu-id="85b30-109">`EndCustomDump` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="85b30-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="85b30-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85b30-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85b30-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="85b30-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85b30-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85b30-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85b30-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="85b30-113">The call timed out.</span></span>|  
|<span data-ttu-id="85b30-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85b30-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85b30-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="85b30-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85b30-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85b30-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85b30-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="85b30-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85b30-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85b30-118">E_FAIL</span></span>|<span data-ttu-id="85b30-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="85b30-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85b30-120">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="85b30-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85b30-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85b30-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85b30-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85b30-122">Remarks</span></span>  
 <span data-ttu-id="85b30-123">El `EndCustomDump` método borra la configuración de volcado de pila personalizada establecida por una llamada anterior a la `BeginCustomDump` método y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="85b30-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="85b30-124">Debe llamarse una vez finalizado el volcado de pila personalizada.</span><span class="sxs-lookup"><span data-stu-id="85b30-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="85b30-125">Error al llamar a `EndCustomDump` provoca la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="85b30-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85b30-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85b30-126">Requirements</span></span>  
 <span data-ttu-id="85b30-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85b30-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85b30-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85b30-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85b30-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85b30-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85b30-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85b30-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b30-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="85b30-131">See also</span></span>

- [<span data-ttu-id="85b30-132">CustomDumpItem (estructura)</span><span class="sxs-lookup"><span data-stu-id="85b30-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="85b30-133">ECustomDumpFlavor (enumeración)</span><span class="sxs-lookup"><span data-stu-id="85b30-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="85b30-134">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85b30-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
