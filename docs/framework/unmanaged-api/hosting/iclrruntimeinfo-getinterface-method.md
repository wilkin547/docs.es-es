---
description: 'Más información acerca de: ICLRRuntimeInfo:: GetInterface (método)'
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
ms.openlocfilehash: 5a5c55823ff9954735a712423d8aaab1256c947d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637136"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="89d97-103">ICLRRuntimeInfo::GetInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="89d97-103">ICLRRuntimeInfo::GetInterface Method</span></span>

<span data-ttu-id="89d97-104">Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución, como [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)y [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="89d97-104">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="89d97-105">Este método sustituye todas las `CorBindTo` funciones \* de la sección [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="89d97-105">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d97-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89d97-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89d97-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89d97-107">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="89d97-108">de La interfaz CLSID para la coclase.</span><span class="sxs-lookup"><span data-stu-id="89d97-108">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="89d97-109">de IID de la interfaz solicitada `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="89d97-109">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="89d97-110">enuncia Puntero a la interfaz consultada.</span><span class="sxs-lookup"><span data-stu-id="89d97-110">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89d97-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89d97-111">Return Value</span></span>  

 <span data-ttu-id="89d97-112">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="89d97-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="89d97-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89d97-113">HRESULT</span></span>|<span data-ttu-id="89d97-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="89d97-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89d97-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="89d97-115">S_OK</span></span>|<span data-ttu-id="89d97-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="89d97-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="89d97-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="89d97-117">E_POINTER</span></span>|<span data-ttu-id="89d97-118">`ppUnk` es null.</span><span class="sxs-lookup"><span data-stu-id="89d97-118">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="89d97-119">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="89d97-119">E_OUTOFMEMORY</span></span>|<span data-ttu-id="89d97-120">No hay suficiente memoria disponible para controlar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="89d97-120">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="89d97-121">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="89d97-121">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="89d97-122">Un tiempo de ejecución diferente ya estaba enlazado a la Directiva de activación heredada de la versión 2 de CLR.</span><span class="sxs-lookup"><span data-stu-id="89d97-122">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89d97-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89d97-123">Remarks</span></span>  

 <span data-ttu-id="89d97-124">Este método hace que el CLR se cargue pero no se inicialice.</span><span class="sxs-lookup"><span data-stu-id="89d97-124">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="89d97-125">En la tabla siguiente se muestran las combinaciones admitidas para `rclsid` y `riid` .</span><span class="sxs-lookup"><span data-stu-id="89d97-125">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="89d97-126">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="89d97-126">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="89d97-127">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="89d97-127">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="89d97-128">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="89d97-128">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="89d97-129">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="89d97-129">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="89d97-130">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="89d97-130">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="89d97-131">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="89d97-131">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="89d97-132">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="89d97-132">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="89d97-133">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="89d97-133">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="89d97-134">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="89d97-134">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="89d97-135">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="89d97-135">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="89d97-136">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="89d97-136">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="89d97-137">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="89d97-137">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="89d97-138">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="89d97-138">CLSID_CLRStrongName</span></span>|<span data-ttu-id="89d97-139">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="89d97-139">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89d97-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89d97-140">Requirements</span></span>  

 <span data-ttu-id="89d97-141">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89d97-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d97-142">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="89d97-142">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="89d97-143">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89d97-143">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89d97-144">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d97-144">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d97-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="89d97-145">See also</span></span>

- [<span data-ttu-id="89d97-146">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="89d97-146">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="89d97-147">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="89d97-147">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="89d97-148">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="89d97-148">Hosting</span></span>](index.md)
