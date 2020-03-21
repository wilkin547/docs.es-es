---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176414"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="48f40-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="48f40-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="48f40-103">Llama al método especificado del tipo especificado en el ensamblado administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="48f40-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f40-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48f40-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48f40-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48f40-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="48f40-106">[en] La ruta <xref:System.Reflection.Assembly> de acceso <xref:System.Type> a la que define el método cuyo se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="48f40-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="48f40-107">[en] El nombre <xref:System.Type> del que define el método que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="48f40-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="48f40-108">[en] El nombre del método que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="48f40-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="48f40-109">[en] El parámetro string que se va a pasar al método.</span><span class="sxs-lookup"><span data-stu-id="48f40-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="48f40-110">[fuera] El valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="48f40-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48f40-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48f40-111">Return Value</span></span>  
  
|<span data-ttu-id="48f40-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48f40-112">HRESULT</span></span>|<span data-ttu-id="48f40-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="48f40-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48f40-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="48f40-114">S_OK</span></span>|<span data-ttu-id="48f40-115">`ExecuteInDefaultAppDomain`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="48f40-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="48f40-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48f40-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48f40-117">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="48f40-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48f40-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48f40-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48f40-119">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="48f40-119">The call timed out.</span></span>|  
|<span data-ttu-id="48f40-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48f40-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48f40-121">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="48f40-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48f40-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48f40-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48f40-123">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="48f40-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48f40-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48f40-124">E_FAIL</span></span>|<span data-ttu-id="48f40-125">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="48f40-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48f40-126">Si un método devuelve E_FAIL, la CRL ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="48f40-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="48f40-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48f40-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48f40-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48f40-128">Remarks</span></span>  
 <span data-ttu-id="48f40-129">El método invocado debe tener la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="48f40-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="48f40-130">donde `pwzMethodName` representa el nombre del método `pwzArgument` invocado y representa el valor de cadena pasado como parámetro a ese método.</span><span class="sxs-lookup"><span data-stu-id="48f40-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="48f40-131">Si el valor HRESULT se `pReturnValue` establece en S_OK, se establece en el valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="48f40-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="48f40-132">De `pReturnValue` lo contrario, no se establece.</span><span class="sxs-lookup"><span data-stu-id="48f40-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f40-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48f40-133">Requirements</span></span>  
 <span data-ttu-id="48f40-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f40-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f40-135">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="48f40-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48f40-136">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48f40-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48f40-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f40-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f40-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48f40-138">See also</span></span>

- [<span data-ttu-id="48f40-139">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48f40-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
