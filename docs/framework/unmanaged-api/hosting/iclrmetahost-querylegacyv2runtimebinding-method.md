---
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
ms.openlocfilehash: b9a51a85bd17e527d4c04b69ca65100a7069607f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703712"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="eff0b-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)</span><span class="sxs-lookup"><span data-stu-id="eff0b-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="eff0b-103">Devuelve una interfaz que representa un tiempo de ejecución en el que se ha enlazado la Directiva de activación heredada, por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en la entrada del archivo de configuración del [ \< elemento> de inicio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) , mediante el uso directo de las API de activación heredadas o llamando al método [ICLRRuntimeInfo:: BindAsLegacyV2Runtime (](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eff0b-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eff0b-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eff0b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eff0b-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="eff0b-106">de Requerido. Actualmente, el único valor válido para este parámetro es `IID_ICLRRuntimeInfo` .</span><span class="sxs-lookup"><span data-stu-id="eff0b-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="eff0b-107">[out] Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eff0b-107">[out] Required.</span></span> <span data-ttu-id="eff0b-108">Cuando este método finaliza, contiene un puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que representa un tiempo de ejecución que se ha enlazado a la Directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="eff0b-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eff0b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eff0b-109">Return Value</span></span>  
 <span data-ttu-id="eff0b-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="eff0b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eff0b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eff0b-111">HRESULT</span></span>|<span data-ttu-id="eff0b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="eff0b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eff0b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="eff0b-113">S_OK</span></span>|<span data-ttu-id="eff0b-114">El método se completó correctamente y devolvió un tiempo de ejecución que se enlazó a la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="eff0b-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="eff0b-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="eff0b-115">S_FALSE</span></span>|<span data-ttu-id="eff0b-116">El método se completó correctamente, pero un tiempo de ejecución heredado no se enlazó.</span><span class="sxs-lookup"><span data-stu-id="eff0b-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="eff0b-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="eff0b-117">E_NOINTERFACE</span></span>|<span data-ttu-id="eff0b-118">El método encontró un tiempo de ejecución que se enlazó a la directiva de activación heredada, pero ese tiempo de ejecución no admite `riid`.</span><span class="sxs-lookup"><span data-stu-id="eff0b-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eff0b-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eff0b-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eff0b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eff0b-120">Requirements</span></span>  
 <span data-ttu-id="eff0b-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eff0b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eff0b-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="eff0b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="eff0b-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eff0b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eff0b-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eff0b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff0b-125">Consulta también</span><span class="sxs-lookup"><span data-stu-id="eff0b-125">See also</span></span>

- [<span data-ttu-id="eff0b-126">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eff0b-126">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="eff0b-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="eff0b-127">Hosting</span></span>](index.md)
