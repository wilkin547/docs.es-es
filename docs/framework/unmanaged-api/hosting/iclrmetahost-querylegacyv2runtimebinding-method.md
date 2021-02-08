---
description: 'Más información acerca de: ICLRMetaHost:: Querylegacyv2runtimebinding ((método)'
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: ae825c2b2dfe2ce5b75ac9b82511215704fa357f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789858"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="eb4f9-103">ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)</span><span class="sxs-lookup"><span data-stu-id="eb4f9-103">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>

<span data-ttu-id="eb4f9-104">Devuelve una interfaz que representa un tiempo de ejecución en el que se ha enlazado la Directiva de activación heredada, por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en la entrada del archivo de configuración del [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) , mediante el uso directo de las API de activación heredadas o llamando al método [ICLRRuntimeInfo:: BindAsLegacyV2Runtime (](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb4f9-104">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb4f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb4f9-105">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb4f9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb4f9-106">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="eb4f9-107">de Requerido. Actualmente, el único valor válido para este parámetro es `IID_ICLRRuntimeInfo` .</span><span class="sxs-lookup"><span data-stu-id="eb4f9-107">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="eb4f9-108">[out] Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-108">[out] Required.</span></span> <span data-ttu-id="eb4f9-109">Cuando este método finaliza, contiene un puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que representa un tiempo de ejecución que se ha enlazado a la Directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-109">When this method returns, contains a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb4f9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eb4f9-110">Return Value</span></span>  

 <span data-ttu-id="eb4f9-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eb4f9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb4f9-112">HRESULT</span></span>|<span data-ttu-id="eb4f9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb4f9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb4f9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb4f9-114">S_OK</span></span>|<span data-ttu-id="eb4f9-115">El método se completó correctamente y devolvió un tiempo de ejecución que se enlazó a la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-115">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="eb4f9-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="eb4f9-116">S_FALSE</span></span>|<span data-ttu-id="eb4f9-117">El método se completó correctamente, pero un tiempo de ejecución heredado no se enlazó.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-117">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="eb4f9-118">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="eb4f9-118">E_NOINTERFACE</span></span>|<span data-ttu-id="eb4f9-119">El método encontró un tiempo de ejecución que se enlazó a la directiva de activación heredada, pero ese tiempo de ejecución no admite `riid`.</span><span class="sxs-lookup"><span data-stu-id="eb4f9-119">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb4f9-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb4f9-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb4f9-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb4f9-121">Requirements</span></span>  

 <span data-ttu-id="eb4f9-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb4f9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb4f9-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="eb4f9-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="eb4f9-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb4f9-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb4f9-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb4f9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4f9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb4f9-126">See also</span></span>

- [<span data-ttu-id="eb4f9-127">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb4f9-127">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="eb4f9-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="eb4f9-128">Hosting</span></span>](index.md)
