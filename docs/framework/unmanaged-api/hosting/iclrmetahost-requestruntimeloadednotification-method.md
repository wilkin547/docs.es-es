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
ms.openlocfilehash: 6813f72f9d27aeff90f797a6ca9370b22e03e6f0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703696"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="9818c-102">ICLRMetaHost::RequestRuntimeLoadedNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="9818c-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="9818c-103">Proporciona una función de devolución de llamada que se garantiza que se llamará cuando una versión de Common Language Runtime (CLR) se cargue por primera vez, pero no se haya iniciado todavía.</span><span class="sxs-lookup"><span data-stu-id="9818c-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="9818c-104">Este método reemplaza a la función [LockClrVersion](lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9818c-104">This method supersedes the [LockClrVersion](lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9818c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9818c-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9818c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9818c-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="9818c-107">de Función de devolución de llamada que se invoca cuando se ha cargado un nuevo tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9818c-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9818c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9818c-108">Return Value</span></span>  
 <span data-ttu-id="9818c-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9818c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9818c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9818c-110">HRESULT</span></span>|<span data-ttu-id="9818c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9818c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9818c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9818c-112">S_OK</span></span>|<span data-ttu-id="9818c-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9818c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9818c-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9818c-114">E_POINTER</span></span>|<span data-ttu-id="9818c-115">`pCallbackFunction` es null.</span><span class="sxs-lookup"><span data-stu-id="9818c-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9818c-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9818c-116">Remarks</span></span>  
 <span data-ttu-id="9818c-117">La devolución de llamada funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9818c-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="9818c-118">La devolución de llamada se invoca solo cuando se carga por primera vez un tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9818c-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="9818c-119">No se invoca la devolución de llamada para las cargas reentrantes del mismo tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9818c-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="9818c-120">En el caso de las cargas de tiempo de ejecución no reentrantes, se serializan las llamadas a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9818c-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="9818c-121">La función de devolución de llamada tiene el prototipo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9818c-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="9818c-122">Los prototipos de función de devolución de llamada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9818c-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="9818c-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="9818c-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="9818c-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="9818c-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="9818c-125">Si el host intenta cargar o hacer que otro Runtime se cargue de forma reentrante, los `pfnCallbackThreadSet` `pfnCallbackThreadUnset` parámetros y que se proporcionan en la función de devolución de llamada deben usarse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9818c-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="9818c-126">`pfnCallbackThreadSet`debe ser invocado por el subproceso que puede producir una carga en tiempo de ejecución antes de que se intente una carga de este tipo.</span><span class="sxs-lookup"><span data-stu-id="9818c-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="9818c-127">`pfnCallbackThreadUnset`se debe llamar a cuando el subproceso ya no producirá una carga de este tipo en tiempo de ejecución (y antes de devolver desde la devolución de llamada inicial).</span><span class="sxs-lookup"><span data-stu-id="9818c-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="9818c-128">`pfnCallbackThreadSet`y `pfnCallbackThreadUnset` son no reentrantes.</span><span class="sxs-lookup"><span data-stu-id="9818c-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9818c-129">Las aplicaciones host no deben llamar a `pfnCallbackThreadSet` y `pfnCallbackThreadUnset` fuera del ámbito del `pCallbackFunction` parámetro.</span><span class="sxs-lookup"><span data-stu-id="9818c-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9818c-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9818c-130">Requirements</span></span>  
 <span data-ttu-id="9818c-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9818c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9818c-132">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9818c-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9818c-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9818c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9818c-134">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9818c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9818c-135">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9818c-135">See also</span></span>

- [<span data-ttu-id="9818c-136">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9818c-136">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="9818c-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9818c-137">Hosting</span></span>](index.md)
