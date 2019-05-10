---
title: ICLRMetaHost::RequestRuntimeLoadedNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87afb19736a484d24bde56cc34854dcd26c6b53b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64755695"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="8f46a-102">ICLRMetaHost::RequestRuntimeLoadedNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="8f46a-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="8f46a-103">Proporciona una función de devolución de llamada que se garantiza que se llama cuando una versión de common language runtime (CLR) se carga por primera vez, pero aún no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="8f46a-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="8f46a-104">Este método reemplaza el [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="8f46a-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f46a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f46a-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f46a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f46a-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="8f46a-107">[in] La función de devolución de llamada que se invoca cuando se ha cargado un nuevo tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f46a-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f46a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f46a-108">Return Value</span></span>  
 <span data-ttu-id="8f46a-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="8f46a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8f46a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f46a-110">HRESULT</span></span>|<span data-ttu-id="8f46a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f46a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f46a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f46a-112">S_OK</span></span>|<span data-ttu-id="8f46a-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8f46a-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="8f46a-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8f46a-114">E_POINTER</span></span>|<span data-ttu-id="8f46a-115">`pCallbackFunction` es null.</span><span class="sxs-lookup"><span data-stu-id="8f46a-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f46a-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f46a-116">Remarks</span></span>  
 <span data-ttu-id="8f46a-117">La devolución de llamada funciona de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f46a-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="8f46a-118">La devolución de llamada se invoca sólo cuando se carga un tiempo de ejecución por primera vez.</span><span class="sxs-lookup"><span data-stu-id="8f46a-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="8f46a-119">No se invoca la devolución de llamada para las cargas reentrantes del mismo runtime.</span><span class="sxs-lookup"><span data-stu-id="8f46a-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="8f46a-120">Para las cargas no reentrante en tiempo de ejecución, se serializan las llamadas a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="8f46a-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="8f46a-121">La función de devolución de llamada tiene el siguiente prototipo:</span><span class="sxs-lookup"><span data-stu-id="8f46a-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="8f46a-122">Los prototipos de función de devolución de llamada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f46a-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="8f46a-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="8f46a-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="8f46a-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="8f46a-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="8f46a-125">Si el host intenta cargar o producir otro tiempo de ejecución que se cargue en un modo reentrante, la `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` parámetros que se proporcionan en la devolución de llamada de función debe usarse en la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8f46a-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="8f46a-126">`pfnCallbackThreadSet` debe llamarse por el subproceso que podría causar una carga en tiempo de ejecución antes de intenta una carga de este tipo.</span><span class="sxs-lookup"><span data-stu-id="8f46a-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="8f46a-127">`pfnCallbackThreadUnset` se debe llamar cuando el subproceso ya no hará que la carga de tiempo de ejecución (y antes de abandonar la devolución de llamada inicial).</span><span class="sxs-lookup"><span data-stu-id="8f46a-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="8f46a-128">`pfnCallbackThreadSet` y `pfnCallbackThreadUnset` son ambos no reentrante.</span><span class="sxs-lookup"><span data-stu-id="8f46a-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f46a-129">No deben llamar las aplicaciones host `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` fuera del ámbito de la `pCallbackFunction` parámetro.</span><span class="sxs-lookup"><span data-stu-id="8f46a-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f46a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f46a-130">Requirements</span></span>  
 <span data-ttu-id="8f46a-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f46a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f46a-132">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8f46a-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f46a-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f46a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f46a-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f46a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f46a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f46a-135">See also</span></span>

- [<span data-ttu-id="8f46a-136">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f46a-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="8f46a-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8f46a-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
