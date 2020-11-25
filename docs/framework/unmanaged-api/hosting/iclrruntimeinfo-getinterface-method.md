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
ms.openlocfilehash: 192163ed8af680e39f7f3a03aee3f46546bc7450
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732078"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="06c9d-102">ICLRRuntimeInfo::GetInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="06c9d-102">ICLRRuntimeInfo::GetInterface Method</span></span>

<span data-ttu-id="06c9d-103">Carga el CLR en el proceso actual y devuelve punteros de interfaz en tiempo de ejecución, como [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)y [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="06c9d-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="06c9d-104">Este método sustituye todas las `CorBindTo` funciones \* de la sección [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="06c9d-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c9d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06c9d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06c9d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06c9d-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="06c9d-107">de La interfaz CLSID para la coclase.</span><span class="sxs-lookup"><span data-stu-id="06c9d-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="06c9d-108">de IID de la interfaz solicitada `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="06c9d-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="06c9d-109">enuncia Puntero a la interfaz consultada.</span><span class="sxs-lookup"><span data-stu-id="06c9d-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06c9d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="06c9d-110">Return Value</span></span>  

 <span data-ttu-id="06c9d-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="06c9d-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="06c9d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06c9d-112">HRESULT</span></span>|<span data-ttu-id="06c9d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="06c9d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06c9d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="06c9d-114">S_OK</span></span>|<span data-ttu-id="06c9d-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="06c9d-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="06c9d-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="06c9d-116">E_POINTER</span></span>|<span data-ttu-id="06c9d-117">`ppUnk` es null.</span><span class="sxs-lookup"><span data-stu-id="06c9d-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="06c9d-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="06c9d-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="06c9d-119">No hay suficiente memoria disponible para controlar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="06c9d-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="06c9d-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="06c9d-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="06c9d-121">Un tiempo de ejecución diferente ya estaba enlazado a la Directiva de activación heredada de la versión 2 de CLR.</span><span class="sxs-lookup"><span data-stu-id="06c9d-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06c9d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06c9d-122">Remarks</span></span>  

 <span data-ttu-id="06c9d-123">Este método hace que el CLR se cargue pero no se inicialice.</span><span class="sxs-lookup"><span data-stu-id="06c9d-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="06c9d-124">En la tabla siguiente se muestran las combinaciones admitidas para `rclsid` y `riid` .</span><span class="sxs-lookup"><span data-stu-id="06c9d-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="06c9d-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="06c9d-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="06c9d-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="06c9d-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="06c9d-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="06c9d-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="06c9d-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="06c9d-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="06c9d-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="06c9d-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="06c9d-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="06c9d-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="06c9d-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="06c9d-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="06c9d-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="06c9d-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="06c9d-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="06c9d-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="06c9d-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="06c9d-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="06c9d-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="06c9d-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="06c9d-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="06c9d-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="06c9d-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="06c9d-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="06c9d-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="06c9d-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06c9d-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06c9d-139">Requirements</span></span>  

 <span data-ttu-id="06c9d-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06c9d-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06c9d-141">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="06c9d-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="06c9d-142">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06c9d-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06c9d-143">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06c9d-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c9d-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06c9d-144">See also</span></span>

- [<span data-ttu-id="06c9d-145">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06c9d-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="06c9d-146">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="06c9d-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="06c9d-147">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="06c9d-147">Hosting</span></span>](index.md)
