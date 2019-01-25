---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c85888e9d29e7b3ae6ad76d1e534e08a4603ed2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499030"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="3cec9-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)</span><span class="sxs-lookup"><span data-stu-id="3cec9-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="3cec9-103">Enlaza el tiempo de ejecución actual para todas heredado common language runtime (CLR) versión 2 activación Directiva las decisiones.</span><span class="sxs-lookup"><span data-stu-id="3cec9-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cec9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cec9-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3cec9-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3cec9-105">Return Value</span></span>  
 <span data-ttu-id="3cec9-106">Este método devuelve los siguientes HRESULT concretos:</span><span class="sxs-lookup"><span data-stu-id="3cec9-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="3cec9-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cec9-107">HRESULT</span></span>|<span data-ttu-id="3cec9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cec9-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cec9-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cec9-109">S_OK</span></span>|<span data-ttu-id="3cec9-110">Enlace se ha realizado correctamente o ya estaba enlazada este tiempo de ejecución que CLR versión 2 activación directiva runtime heredado.</span><span class="sxs-lookup"><span data-stu-id="3cec9-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="3cec9-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="3cec9-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="3cec9-112">Un runtime diferente ya estaba enlazado a la directiva de 2 activación de versión CLR heredada.</span><span class="sxs-lookup"><span data-stu-id="3cec9-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cec9-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cec9-113">Remarks</span></span>  
 <span data-ttu-id="3cec9-114">Si ya está enlazado el tiempo de ejecución actual para todos los heredados CLR versión 2 activación las decisiones de directiva (por ejemplo, mediante el `useLegacyV2RuntimeActivationPolicy` atributo el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) en el archivo de configuración), este método no devuelve un resultado de error; en su lugar, el resultado es S_OK, tal como lo sería si el método tenía enlazar correctamente la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="3cec9-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cec9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cec9-115">Requirements</span></span>  
 <span data-ttu-id="3cec9-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cec9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cec9-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3cec9-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3cec9-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cec9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cec9-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cec9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cec9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cec9-120">See also</span></span>
- [<span data-ttu-id="3cec9-121">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cec9-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3cec9-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="3cec9-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3cec9-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3cec9-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="3cec9-124">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="3cec9-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
