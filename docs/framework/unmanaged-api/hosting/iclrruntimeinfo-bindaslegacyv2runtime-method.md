---
description: 'Más información acerca de: ICLRRuntimeInfo:: Bindaslegacyv2runtime ((método)'
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
ms.openlocfilehash: 77b340cba18ea86546e1a8f4a17933f09289b1de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637188"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="4395b-103">ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)</span><span class="sxs-lookup"><span data-stu-id="4395b-103">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>

<span data-ttu-id="4395b-104">Enlaza el tiempo de ejecución actual para todas las decisiones de la Directiva de activación de la versión 2 de Common Language Runtime heredada (CLR).</span><span class="sxs-lookup"><span data-stu-id="4395b-104">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4395b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4395b-105">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4395b-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4395b-106">Return Value</span></span>  

 <span data-ttu-id="4395b-107">Este método devuelve los siguientes HRESULT específicos:</span><span class="sxs-lookup"><span data-stu-id="4395b-107">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="4395b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4395b-108">HRESULT</span></span>|<span data-ttu-id="4395b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4395b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4395b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4395b-110">S_OK</span></span>|<span data-ttu-id="4395b-111">El enlace se realizó correctamente o este tiempo de ejecución ya estaba enlazado como el Runtime heredado de la Directiva de activación de la versión 2 de CLR.</span><span class="sxs-lookup"><span data-stu-id="4395b-111">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="4395b-112">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="4395b-112">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="4395b-113">Un tiempo de ejecución diferente ya estaba enlazado a la Directiva de activación heredada de la versión 2 de CLR.</span><span class="sxs-lookup"><span data-stu-id="4395b-113">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4395b-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4395b-114">Remarks</span></span>  

 <span data-ttu-id="4395b-115">Si el tiempo de ejecución actual ya está enlazado a todas las decisiones de la Directiva de activación heredada de la versión 2 de CLR (por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en el [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) del archivo de configuración), este método no devuelve un resultado de error; en su lugar, el resultado es S_OK, del mismo modo que si el método tuviera la Directiva de activación heredada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4395b-115">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4395b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4395b-116">Requirements</span></span>  

 <span data-ttu-id="4395b-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4395b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4395b-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4395b-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4395b-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4395b-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4395b-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4395b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4395b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4395b-121">See also</span></span>

- [<span data-ttu-id="4395b-122">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4395b-122">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="4395b-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4395b-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4395b-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="4395b-124">Hosting</span></span>](index.md)
- [<span data-ttu-id="4395b-125">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="4395b-125">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
