---
title: CorRuntimeHost (Coclase)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23bee1a79dfb54a696495fdb61a7ba9ba4b4c143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="4e7e2-102">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="4e7e2-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="4e7e2-103">Proporciona interfaces para administrar las aplicaciones que se están ejecutando por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="4e7e2-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e7e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e7e2-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="4e7e2-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="4e7e2-105">Interfaces</span></span>  
  
|<span data-ttu-id="4e7e2-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="4e7e2-106">Interface</span></span>|<span data-ttu-id="4e7e2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e7e2-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="4e7e2-108">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e7e2-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="4e7e2-109">Proporciona métodos para la configuración de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4e7e2-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="4e7e2-110">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e7e2-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="4e7e2-111">Proporciona métodos que permiten al host iniciar y detener de forma explícita, common language runtime para crear y configurar dominios de aplicación, tener acceso al dominio predeterminado y enumerar todos los dominios que se ejecuta en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4e7e2-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="4e7e2-112">IDebuggerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e7e2-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="4e7e2-113">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="4e7e2-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="4e7e2-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e7e2-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="4e7e2-115">Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="4e7e2-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="4e7e2-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="4e7e2-116">"IValidator"</span></span>|<span data-ttu-id="4e7e2-117">Proporciona métodos para la validación de imágenes ejecutables portables y los informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="4e7e2-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e7e2-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e7e2-118">Requirements</span></span>  
 <span data-ttu-id="4e7e2-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e7e2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e7e2-120">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="4e7e2-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4e7e2-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e7e2-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e7e2-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e7e2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e7e2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e7e2-123">See Also</span></span>  
 [<span data-ttu-id="4e7e2-124">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="4e7e2-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
