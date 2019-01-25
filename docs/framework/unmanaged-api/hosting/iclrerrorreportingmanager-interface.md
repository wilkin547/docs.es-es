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
ms.openlocfilehash: d10fe0240073464e3c2677343288e5379840885d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732796"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="e532c-102">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e532c-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="e532c-103">Proporciona métodos que permiten al host configurar volcados de pila personalizados para informes de errores.</span><span class="sxs-lookup"><span data-stu-id="e532c-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e532c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e532c-104">Methods</span></span>  
  
|<span data-ttu-id="e532c-105">Método</span><span class="sxs-lookup"><span data-stu-id="e532c-105">Method</span></span>|<span data-ttu-id="e532c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e532c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e532c-107">BeginCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="e532c-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="e532c-108">Especifica la configuración de los volcados de pila personalizados para informes de errores.</span><span class="sxs-lookup"><span data-stu-id="e532c-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="e532c-109">EndCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="e532c-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="e532c-110">Borra la configuración de volcado de pila personalizada que se ha establecido mediante una llamada anterior a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="e532c-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="e532c-111">GetBucketParametersForCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="e532c-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="e532c-112">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e532c-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e532c-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e532c-113">Remarks</span></span>  
 <span data-ttu-id="e532c-114">El `BeginCustomDump` método establece la configuración de volcado de pila personalizada.</span><span class="sxs-lookup"><span data-stu-id="e532c-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="e532c-115">El `EndCustomDump` método borra la configuración de volcado de pila personalizados y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="e532c-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="e532c-116">Debe llamarse una vez finalizado el volcado personalizado.</span><span class="sxs-lookup"><span data-stu-id="e532c-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e532c-117">Error al llamar a `EndCustomDump` provoca la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="e532c-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e532c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e532c-118">Requirements</span></span>  
 <span data-ttu-id="e532c-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e532c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e532c-120">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e532c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e532c-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e532c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e532c-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e532c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e532c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e532c-123">See also</span></span>
- [<span data-ttu-id="e532c-124">ECustomDumpItemKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="e532c-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="e532c-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e532c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
