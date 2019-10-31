---
title: LockClrVersion (Función)
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133773"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="82f99-102">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="82f99-102">LockClrVersion Function</span></span>
<span data-ttu-id="82f99-103">Permite al host determinar qué versión de Common Language Runtime (CLR) se utilizará en el proceso antes de inicializar explícitamente CLR.</span><span class="sxs-lookup"><span data-stu-id="82f99-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="82f99-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="82f99-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82f99-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82f99-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82f99-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="82f99-107">de Función a la que llamará CLR al inicializarse.</span><span class="sxs-lookup"><span data-stu-id="82f99-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="82f99-108">de Función a la que llamará el host para informar al CLR de que se está iniciando la inicialización.</span><span class="sxs-lookup"><span data-stu-id="82f99-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="82f99-109">de Función a la que llamará el host para informar al CLR de que la inicialización se ha completado.</span><span class="sxs-lookup"><span data-stu-id="82f99-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82f99-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82f99-110">Return Value</span></span>  
 <span data-ttu-id="82f99-111">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="82f99-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="82f99-112">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="82f99-112">Return code</span></span>|<span data-ttu-id="82f99-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="82f99-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="82f99-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="82f99-114">S_OK</span></span>|<span data-ttu-id="82f99-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="82f99-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="82f99-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="82f99-116">E_INVALIDARG</span></span>|<span data-ttu-id="82f99-117">Uno o varios argumentos son NULL.</span><span class="sxs-lookup"><span data-stu-id="82f99-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82f99-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82f99-118">Remarks</span></span>  
 <span data-ttu-id="82f99-119">El host llama a `LockClrVersion` antes de inicializar el CLR.</span><span class="sxs-lookup"><span data-stu-id="82f99-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="82f99-120">`LockClrVersion` toma tres parámetros, todos ellos son devoluciones de llamada de tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="82f99-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="82f99-121">Este tipo se define como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="82f99-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="82f99-122">Los siguientes pasos se producen tras la inicialización del tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="82f99-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="82f99-123">El host llama a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o a una de las otras funciones de inicialización en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="82f99-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="82f99-124">Como alternativa, el host podría inicializar el tiempo de ejecución mediante la activación de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="82f99-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="82f99-125">El Runtime llama a la función especificada por el parámetro `hostCallback`.</span><span class="sxs-lookup"><span data-stu-id="82f99-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="82f99-126">A continuación, la función especificada por `hostCallback` realiza la siguiente secuencia de llamadas:</span><span class="sxs-lookup"><span data-stu-id="82f99-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="82f99-127">Función especificada por el parámetro `pBeginHostSetup`.</span><span class="sxs-lookup"><span data-stu-id="82f99-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="82f99-128">`CorBindToRuntimeEx` (u otra función de inicialización en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="82f99-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="82f99-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="82f99-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="82f99-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="82f99-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="82f99-131">Función especificada por el parámetro `pEndHostSetup`.</span><span class="sxs-lookup"><span data-stu-id="82f99-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="82f99-132">Todas las llamadas de `pBeginHostSetup` a `pEndHostSetup` deben producirse en un único subproceso o fibra, con la misma pila lógica.</span><span class="sxs-lookup"><span data-stu-id="82f99-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="82f99-133">Este subproceso puede ser diferente del subproceso en el que se llama a `hostCallback`.</span><span class="sxs-lookup"><span data-stu-id="82f99-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f99-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82f99-134">Requirements</span></span>  
 <span data-ttu-id="82f99-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82f99-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f99-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="82f99-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82f99-137">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="82f99-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82f99-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f99-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f99-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="82f99-139">See also</span></span>

- [<span data-ttu-id="82f99-140">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="82f99-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
