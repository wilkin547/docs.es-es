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
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129253"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="9ba18-102">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ba18-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="9ba18-103">Proporciona métodos que permiten al host configurar volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ba18-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ba18-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9ba18-104">Methods</span></span>  
  
|<span data-ttu-id="9ba18-105">Método</span><span class="sxs-lookup"><span data-stu-id="9ba18-105">Method</span></span>|<span data-ttu-id="9ba18-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ba18-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ba18-107">BeginCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="9ba18-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="9ba18-108">Especifica la configuración de los volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="9ba18-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="9ba18-109">EndCustomDump (método)</span><span class="sxs-lookup"><span data-stu-id="9ba18-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="9ba18-110">Borra la configuración de volcado de la pila personalizada establecida por una llamada anterior a `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="9ba18-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="9ba18-111">GetBucketParametersForCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="9ba18-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="9ba18-112">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="9ba18-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ba18-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ba18-113">Remarks</span></span>  
 <span data-ttu-id="9ba18-114">El método `BeginCustomDump` establece la configuración personalizada del volcado de la pila.</span><span class="sxs-lookup"><span data-stu-id="9ba18-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="9ba18-115">El método `EndCustomDump` borra la configuración de volcado de la pila personalizada y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="9ba18-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="9ba18-116">Se debe llamar después de completar el volcado de memoria personalizado.</span><span class="sxs-lookup"><span data-stu-id="9ba18-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9ba18-117">Si no se llama a `EndCustomDump`, se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="9ba18-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ba18-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ba18-118">Requirements</span></span>  
 <span data-ttu-id="9ba18-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba18-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba18-120">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ba18-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ba18-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9ba18-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ba18-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba18-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba18-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ba18-123">See also</span></span>

- [<span data-ttu-id="9ba18-124">ECustomDumpItemKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="9ba18-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="9ba18-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9ba18-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
