---
description: 'Más información acerca de: ICLRRuntimeHost:: GetCLRControl ((método)'
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
ms.openlocfilehash: 832ae03c0126f0c08afa9b5c0312a636ec1de294
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753944"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="b28b0-103">ICLRRuntimeHost::GetCLRControl (Método)</span><span class="sxs-lookup"><span data-stu-id="b28b0-103">ICLRRuntimeHost::GetCLRControl Method</span></span>

<span data-ttu-id="b28b0-104">Obtiene un puntero de interfaz de tipo [ICLRControl interface](iclrcontrol-interface.md) que los hosts pueden utilizar para personalizar aspectos del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b28b0-104">Gets an interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b28b0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28b0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b28b0-106">Parameters</span></span>  

 `pCLRControl`  
 <span data-ttu-id="b28b0-107">enuncia Puntero de interfaz de tipo [ICLRControl](iclrcontrol-interface.md) que permite a los hosts configurar aspectos adicionales de CLR.</span><span class="sxs-lookup"><span data-stu-id="b28b0-107">[out] An interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28b0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b28b0-108">Return Value</span></span>  
  
|<span data-ttu-id="b28b0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b28b0-109">HRESULT</span></span>|<span data-ttu-id="b28b0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b28b0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b28b0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b28b0-111">S_OK</span></span>|<span data-ttu-id="b28b0-112">`GetCLRControl` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b28b0-112">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="b28b0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b28b0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b28b0-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b28b0-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b28b0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b28b0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b28b0-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b28b0-116">The call timed out.</span></span>|  
|<span data-ttu-id="b28b0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b28b0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b28b0-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b28b0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b28b0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b28b0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b28b0-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b28b0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b28b0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b28b0-121">E_FAIL</span></span>|<span data-ttu-id="b28b0-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b28b0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b28b0-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b28b0-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b28b0-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b28b0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b28b0-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b28b0-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b28b0-126">El CLR ya se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="b28b0-126">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b28b0-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b28b0-127">Remarks</span></span>  

 <span data-ttu-id="b28b0-128">`ICLRControl` proporciona el método del [método GetCLRManager (](iclrcontrol-getclrmanager-method.md) , que permite al host obtener un puntero de interfaz a uno de los tipos de administrador.</span><span class="sxs-lookup"><span data-stu-id="b28b0-128">`ICLRControl` provides the [GetCLRManager Method](iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28b0-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b28b0-129">Requirements</span></span>  

 <span data-ttu-id="b28b0-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28b0-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28b0-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b28b0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b28b0-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b28b0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b28b0-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28b0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28b0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b28b0-134">See also</span></span>

- [<span data-ttu-id="b28b0-135">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b28b0-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b28b0-136">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b28b0-136">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
