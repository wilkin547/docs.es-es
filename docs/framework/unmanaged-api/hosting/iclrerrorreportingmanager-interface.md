---
description: 'Más información acerca de: ICLRErrorReportingManager (interfaz)'
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
ms.openlocfilehash: 094fe52858983fd0e1e5826e823932cb150b6087
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689279"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="257b4-103">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="257b4-103">ICLRErrorReportingManager Interface</span></span>

<span data-ttu-id="257b4-104">Proporciona métodos que permiten al host configurar volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="257b4-104">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="257b4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="257b4-105">Methods</span></span>  
  
|<span data-ttu-id="257b4-106">Método</span><span class="sxs-lookup"><span data-stu-id="257b4-106">Method</span></span>|<span data-ttu-id="257b4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="257b4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="257b4-108">Método BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="257b4-108">BeginCustomDump Method</span></span>](iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="257b4-109">Especifica la configuración de los volcados de pila personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="257b4-109">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="257b4-110">Método EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="257b4-110">EndCustomDump Method</span></span>](iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="257b4-111">Borra la configuración de volcado de la pila personalizada establecida por una llamada anterior a `BeginCustomDump` .</span><span class="sxs-lookup"><span data-stu-id="257b4-111">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="257b4-112">Método GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="257b4-112">GetBucketParametersForCurrentException Method</span></span>](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="257b4-113">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="257b4-113">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="257b4-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="257b4-114">Remarks</span></span>  

 <span data-ttu-id="257b4-115">El `BeginCustomDump` método establece la configuración personalizada del volcado de la pila.</span><span class="sxs-lookup"><span data-stu-id="257b4-115">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="257b4-116">El `EndCustomDump` método borra la configuración de volcado de la pila personalizada y libera cualquier estado asociado.</span><span class="sxs-lookup"><span data-stu-id="257b4-116">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="257b4-117">Se debe llamar después de completar el volcado de memoria personalizado.</span><span class="sxs-lookup"><span data-stu-id="257b4-117">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="257b4-118">Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="257b4-118">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="257b4-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="257b4-119">Requirements</span></span>  

 <span data-ttu-id="257b4-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="257b4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="257b4-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="257b4-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="257b4-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="257b4-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="257b4-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="257b4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257b4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="257b4-124">See also</span></span>

- [<span data-ttu-id="257b4-125">ECustomDumpItemKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="257b4-125">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="257b4-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="257b4-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
