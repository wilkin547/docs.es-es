---
title: "ICLRRuntimeInfo::GetInterface (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0049b4e60f803fbc9ec64e7f20273b1d5729e67f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="cae5f-102">ICLRRuntimeInfo::GetInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="cae5f-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="cae5f-103">Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución como [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), y [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cae5f-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="cae5f-104">Este método reemplaza a todos los `CorBindTo`* las funciones en el [funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) sección.</span><span class="sxs-lookup"><span data-stu-id="cae5f-104">This method supersedes all the `CorBindTo`* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae5f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cae5f-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cae5f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cae5f-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="cae5f-107">[in] La interfaz CLSID de la coclase.</span><span class="sxs-lookup"><span data-stu-id="cae5f-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="cae5f-108">[in] El IID de solicitado `rclsid` interfaz.</span><span class="sxs-lookup"><span data-stu-id="cae5f-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="cae5f-109">[out] Un puntero a la interfaz consultado.</span><span class="sxs-lookup"><span data-stu-id="cae5f-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cae5f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cae5f-110">Return Value</span></span>  
 <span data-ttu-id="cae5f-111">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="cae5f-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cae5f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cae5f-112">HRESULT</span></span>|<span data-ttu-id="cae5f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae5f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cae5f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="cae5f-114">S_OK</span></span>|<span data-ttu-id="cae5f-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cae5f-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="cae5f-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="cae5f-116">E_POINTER</span></span>|<span data-ttu-id="cae5f-117">`ppUnk` es null.</span><span class="sxs-lookup"><span data-stu-id="cae5f-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="cae5f-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cae5f-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cae5f-119">No hay suficiente memoria disponible para atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cae5f-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="cae5f-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="cae5f-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="cae5f-121">Un runtime diferente ya se enlazó a la directiva de activación 2 de versión CLR heredada.</span><span class="sxs-lookup"><span data-stu-id="cae5f-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cae5f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cae5f-122">Remarks</span></span>  
 <span data-ttu-id="cae5f-123">Este método hace que el CLR debe ser cargado pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="cae5f-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="cae5f-124">La tabla siguiente muestran las combinaciones admitidas para `rclsid` y `riid`.</span><span class="sxs-lookup"><span data-stu-id="cae5f-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="cae5f-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="cae5f-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="cae5f-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="cae5f-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="cae5f-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="cae5f-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="cae5f-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="cae5f-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="cae5f-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cae5f-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="cae5f-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cae5f-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="cae5f-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cae5f-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="cae5f-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cae5f-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="cae5f-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="cae5f-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="cae5f-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="cae5f-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="cae5f-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="cae5f-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="cae5f-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="cae5f-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="cae5f-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cae5f-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="cae5f-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cae5f-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cae5f-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cae5f-139">Requirements</span></span>  
 <span data-ttu-id="cae5f-140">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cae5f-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae5f-141">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cae5f-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cae5f-142">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cae5f-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cae5f-143">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cae5f-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae5f-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="cae5f-144">See Also</span></span>  
 [<span data-ttu-id="cae5f-145">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cae5f-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="cae5f-146">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cae5f-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="cae5f-147">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cae5f-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
