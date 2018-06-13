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
ms.openlocfilehash: bf9e04ed1d3a68fed120c4c13ad992af1f777244
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433801"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="19cd7-102">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19cd7-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="19cd7-103">Proporciona métodos que permiten al host configurar los volcados de pila personalizados para informes de errores.</span><span class="sxs-lookup"><span data-stu-id="19cd7-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19cd7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="19cd7-104">Methods</span></span>  
  
|<span data-ttu-id="19cd7-105">Método</span><span class="sxs-lookup"><span data-stu-id="19cd7-105">Method</span></span>|<span data-ttu-id="19cd7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="19cd7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19cd7-107">BeginCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="19cd7-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="19cd7-108">Especifica la configuración de los volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="19cd7-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="19cd7-109">EndCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="19cd7-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="19cd7-110">Borra la configuración de volcado de pila personalizada establecida por una llamada anterior a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="19cd7-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="19cd7-111">GetBucketParametersForCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="19cd7-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="19cd7-112">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="19cd7-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19cd7-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19cd7-113">Remarks</span></span>  
 <span data-ttu-id="19cd7-114">El `BeginCustomDump` método establece la configuración de volcado de pila personalizada.</span><span class="sxs-lookup"><span data-stu-id="19cd7-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="19cd7-115">El `EndCustomDump` método borra la configuración de volcado de pila personalizada y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="19cd7-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="19cd7-116">Debe llamarse una vez finalizado el volcado personalizado.</span><span class="sxs-lookup"><span data-stu-id="19cd7-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="19cd7-117">Error al llamar a `EndCustomDump` provoca la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="19cd7-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19cd7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19cd7-118">Requirements</span></span>  
 <span data-ttu-id="19cd7-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19cd7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19cd7-120">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19cd7-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19cd7-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19cd7-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19cd7-122">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19cd7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19cd7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="19cd7-123">See Also</span></span>  
 [<span data-ttu-id="19cd7-124">ECustomDumpItemKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="19cd7-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="19cd7-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="19cd7-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
