---
title: ICLRErrorReportingManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a9d9cff0360e4eb27584fe0f22c1c20396ff8f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966256"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="a9a73-102">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9a73-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="a9a73-103">Proporciona métodos que permiten al host configurar volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a9a73-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9a73-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9a73-104">Methods</span></span>  
  
|<span data-ttu-id="a9a73-105">Método</span><span class="sxs-lookup"><span data-stu-id="a9a73-105">Method</span></span>|<span data-ttu-id="a9a73-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a9a73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9a73-107">BeginCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="a9a73-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="a9a73-108">Especifica la configuración de los volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="a9a73-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="a9a73-109">EndCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="a9a73-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="a9a73-110">Borra la configuración de volcado de la pila personalizada establecida por una llamada anterior a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="a9a73-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="a9a73-111">GetBucketParametersForCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="a9a73-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="a9a73-112">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a9a73-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9a73-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9a73-113">Remarks</span></span>  
 <span data-ttu-id="a9a73-114">El `BeginCustomDump` método establece la configuración personalizada del volcado de la pila.</span><span class="sxs-lookup"><span data-stu-id="a9a73-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="a9a73-115">El `EndCustomDump` método borra la configuración de volcado de la pila personalizada y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="a9a73-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="a9a73-116">Se debe llamar después de completar el volcado de memoria personalizado.</span><span class="sxs-lookup"><span data-stu-id="a9a73-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9a73-117">Si no se `EndCustomDump` llama a, se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="a9a73-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9a73-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9a73-118">Requirements</span></span>  
 <span data-ttu-id="a9a73-119">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9a73-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9a73-120">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9a73-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9a73-121">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9a73-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9a73-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a73-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a73-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9a73-123">See also</span></span>

- [<span data-ttu-id="a9a73-124">ECustomDumpItemKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a9a73-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="a9a73-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a9a73-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
