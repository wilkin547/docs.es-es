---
title: ICLRRuntimeInfo::GetInterface (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 770901d5461d2092ce5f2862624a038caf03e1f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678670"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="a8e63-102">ICLRRuntimeInfo::GetInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="a8e63-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="a8e63-103">Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución como [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), y [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a8e63-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="a8e63-104">Este método reemplaza todos los `CorBindTo`\* funciona en el [funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) sección.</span><span class="sxs-lookup"><span data-stu-id="a8e63-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8e63-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8e63-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8e63-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="a8e63-107">[in] La interfaz CLSID de la coclase.</span><span class="sxs-lookup"><span data-stu-id="a8e63-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="a8e63-108">[in] El IID de solicitado `rclsid` interfaz.</span><span class="sxs-lookup"><span data-stu-id="a8e63-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="a8e63-109">[out] Un puntero a la interfaz consultada.</span><span class="sxs-lookup"><span data-stu-id="a8e63-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8e63-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a8e63-110">Return Value</span></span>  
 <span data-ttu-id="a8e63-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a8e63-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a8e63-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8e63-112">HRESULT</span></span>|<span data-ttu-id="a8e63-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8e63-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8e63-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8e63-114">S_OK</span></span>|<span data-ttu-id="a8e63-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8e63-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="a8e63-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a8e63-116">E_POINTER</span></span>|<span data-ttu-id="a8e63-117">`ppUnk` es null.</span><span class="sxs-lookup"><span data-stu-id="a8e63-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="a8e63-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a8e63-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a8e63-119">No hay suficiente memoria disponible para atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a8e63-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="a8e63-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="a8e63-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="a8e63-121">Un runtime diferente ya estaba enlazado a la directiva de 2 activación de versión CLR heredada.</span><span class="sxs-lookup"><span data-stu-id="a8e63-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8e63-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8e63-122">Remarks</span></span>  
 <span data-ttu-id="a8e63-123">Este método provoca que el CLR que se cargó, pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="a8e63-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="a8e63-124">La siguiente tabla muestra las combinaciones admitidas de `rclsid` y `riid`.</span><span class="sxs-lookup"><span data-stu-id="a8e63-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="a8e63-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="a8e63-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="a8e63-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="a8e63-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="a8e63-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="a8e63-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="a8e63-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="a8e63-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="a8e63-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a8e63-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="a8e63-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a8e63-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="a8e63-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a8e63-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="a8e63-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a8e63-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="a8e63-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="a8e63-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="a8e63-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="a8e63-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="a8e63-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="a8e63-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="a8e63-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a8e63-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="a8e63-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a8e63-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="a8e63-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a8e63-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8e63-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8e63-139">Requirements</span></span>  
 <span data-ttu-id="a8e63-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8e63-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e63-141">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a8e63-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a8e63-142">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8e63-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8e63-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e63-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e63-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8e63-144">See also</span></span>
- [<span data-ttu-id="a8e63-145">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8e63-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a8e63-146">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a8e63-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a8e63-147">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a8e63-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
