---
title: ICLRRuntimeHost::GetCLRControl (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 928ac05fbd3a19a17e7f37674b2a75f8bc799fc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728880"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="8ee73-102">ICLRRuntimeHost::GetCLRControl (Método)</span><span class="sxs-lookup"><span data-stu-id="8ee73-102">ICLRRuntimeHost::GetCLRControl Method</span></span>

<span data-ttu-id="8ee73-103">Obtiene un puntero de interfaz de tipo [ICLRControl interface](iclrcontrol-interface.md) que los hosts pueden utilizar para personalizar aspectos del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8ee73-103">Gets an interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ee73-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ee73-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ee73-105">Parameters</span></span>  

 `pCLRControl`  
 <span data-ttu-id="8ee73-106">enuncia Puntero de interfaz de tipo [ICLRControl](iclrcontrol-interface.md) que permite a los hosts configurar aspectos adicionales de CLR.</span><span class="sxs-lookup"><span data-stu-id="8ee73-106">[out] An interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ee73-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ee73-107">Return Value</span></span>  
  
|<span data-ttu-id="8ee73-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ee73-108">HRESULT</span></span>|<span data-ttu-id="8ee73-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ee73-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ee73-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ee73-110">S_OK</span></span>|<span data-ttu-id="8ee73-111">`GetCLRControl` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8ee73-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="8ee73-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ee73-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ee73-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8ee73-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ee73-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ee73-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ee73-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8ee73-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ee73-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ee73-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ee73-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8ee73-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ee73-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ee73-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ee73-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8ee73-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ee73-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ee73-120">E_FAIL</span></span>|<span data-ttu-id="8ee73-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8ee73-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ee73-122">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8ee73-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ee73-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ee73-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ee73-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8ee73-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8ee73-125">El CLR ya se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="8ee73-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ee73-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ee73-126">Remarks</span></span>  

 <span data-ttu-id="8ee73-127">`ICLRControl` proporciona el método del [método GetCLRManager (](iclrcontrol-getclrmanager-method.md) , que permite al host obtener un puntero de interfaz a uno de los tipos de administrador.</span><span class="sxs-lookup"><span data-stu-id="8ee73-127">`ICLRControl` provides the [GetCLRManager Method](iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ee73-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ee73-128">Requirements</span></span>  

 <span data-ttu-id="8ee73-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ee73-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee73-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8ee73-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ee73-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ee73-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ee73-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ee73-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee73-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ee73-133">See also</span></span>

- [<span data-ttu-id="8ee73-134">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ee73-134">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8ee73-135">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ee73-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
