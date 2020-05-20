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
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703897"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="b796d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)</span><span class="sxs-lookup"><span data-stu-id="b796d-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="b796d-103">Enlaza el tiempo de ejecución actual para todas las decisiones de la Directiva de activación de la versión 2 de Common Language Runtime heredada (CLR).</span><span class="sxs-lookup"><span data-stu-id="b796d-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b796d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b796d-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b796d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b796d-105">Return Value</span></span>  
 <span data-ttu-id="b796d-106">Este método devuelve los siguientes HRESULT específicos:</span><span class="sxs-lookup"><span data-stu-id="b796d-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="b796d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b796d-107">HRESULT</span></span>|<span data-ttu-id="b796d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b796d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b796d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="b796d-109">S_OK</span></span>|<span data-ttu-id="b796d-110">El enlace se realizó correctamente o este tiempo de ejecución ya estaba enlazado como el Runtime heredado de la Directiva de activación de la versión 2 de CLR.</span><span class="sxs-lookup"><span data-stu-id="b796d-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="b796d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="b796d-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="b796d-112">Un tiempo de ejecución diferente ya estaba enlazado a la Directiva de activación heredada de la versión 2 de CLR.</span><span class="sxs-lookup"><span data-stu-id="b796d-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b796d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b796d-113">Remarks</span></span>  
 <span data-ttu-id="b796d-114">Si el tiempo de ejecución actual ya está enlazado a todas las decisiones de la Directiva de activación heredada de la versión 2 de CLR (por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en el [ \< elemento de> de inicio](../../configure-apps/file-schema/startup/startup-element.md) del archivo de configuración), este método no devuelve ningún resultado de error; en su lugar, el resultado es S_OK, del mismo modo que si el método hubiera enlazado correctamente la Directiva</span><span class="sxs-lookup"><span data-stu-id="b796d-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b796d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b796d-115">Requirements</span></span>  
 <span data-ttu-id="b796d-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b796d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b796d-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b796d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b796d-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b796d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b796d-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b796d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b796d-120">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b796d-120">See also</span></span>

- [<span data-ttu-id="b796d-121">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b796d-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b796d-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b796d-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b796d-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b796d-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="b796d-124">\<Startup>, elemento</span><span class="sxs-lookup"><span data-stu-id="b796d-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
