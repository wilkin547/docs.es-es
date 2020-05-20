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
ms.openlocfilehash: 070c52258b66dcc352f2beef81b9a0694b8301ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703290"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="c227d-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="c227d-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="c227d-103">Llama al método especificado del tipo especificado en el ensamblado administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="c227d-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c227d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c227d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c227d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c227d-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="c227d-106">de La ruta de acceso al <xref:System.Reflection.Assembly> que define el <xref:System.Type> cuyo método se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="c227d-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="c227d-107">de Nombre del <xref:System.Type> que define el método que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="c227d-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="c227d-108">de Nombre del método que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="c227d-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="c227d-109">de Parámetro de cadena que se va a pasar al método.</span><span class="sxs-lookup"><span data-stu-id="c227d-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="c227d-110">enuncia El valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="c227d-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c227d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c227d-111">Return Value</span></span>  
  
|<span data-ttu-id="c227d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c227d-112">HRESULT</span></span>|<span data-ttu-id="c227d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c227d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c227d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c227d-114">S_OK</span></span>|<span data-ttu-id="c227d-115">`ExecuteInDefaultAppDomain`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c227d-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="c227d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c227d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c227d-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c227d-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c227d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c227d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c227d-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c227d-119">The call timed out.</span></span>|  
|<span data-ttu-id="c227d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c227d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c227d-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c227d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c227d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c227d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c227d-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c227d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c227d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c227d-124">E_FAIL</span></span>|<span data-ttu-id="c227d-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c227d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c227d-126">Si un método devuelve E_FAIL, la CRL ya no se podrá usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c227d-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="c227d-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c227d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c227d-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c227d-128">Remarks</span></span>  
 <span data-ttu-id="c227d-129">El método invocado debe tener la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="c227d-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="c227d-130">donde `pwzMethodName` representa el nombre del método invocado y `pwzArgument` representa el valor de cadena que se pasa como parámetro a ese método.</span><span class="sxs-lookup"><span data-stu-id="c227d-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="c227d-131">Si el valor HRESULT se establece en S_OK, `pReturnValue` se establece en el valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="c227d-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="c227d-132">De lo contrario, `pReturnValue` no se establece.</span><span class="sxs-lookup"><span data-stu-id="c227d-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c227d-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c227d-133">Requirements</span></span>  
 <span data-ttu-id="c227d-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c227d-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c227d-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c227d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c227d-136">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c227d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c227d-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c227d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c227d-138">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c227d-138">See also</span></span>

- [<span data-ttu-id="c227d-139">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c227d-139">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
