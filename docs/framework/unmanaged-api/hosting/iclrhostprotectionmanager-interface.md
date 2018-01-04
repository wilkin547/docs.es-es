---
title: ICLRHostProtectionManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager
helpviewer_keywords: ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37b1aaeef1d4c375f36ad043124287fc3b41e3fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="9605e-102">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9605e-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="9605e-103">Permite al host bloquear clases administradas específicas, métodos, propiedades y campos de ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="9605e-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9605e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9605e-104">Methods</span></span>  
  
|<span data-ttu-id="9605e-105">Método</span><span class="sxs-lookup"><span data-stu-id="9605e-105">Method</span></span>|<span data-ttu-id="9605e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9605e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9605e-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="9605e-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="9605e-108">Proporciona una garantía de que nunca se producirán ciertas condiciones de carrera poco frecuentes que pueden provocar errores de tiempo de ejecución (CLR) de lenguaje común irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="9605e-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="9605e-109">SetProtectedCategories (método)</span><span class="sxs-lookup"><span data-stu-id="9605e-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="9605e-110">Especifica las categorías de tipos administrados y miembros que se deben bloquear ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="9605e-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9605e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9605e-111">Requirements</span></span>  
 <span data-ttu-id="9605e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9605e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9605e-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9605e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9605e-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9605e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9605e-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9605e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9605e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9605e-116">See Also</span></span>  
 [<span data-ttu-id="9605e-117">EApiCategories (enumeración)</span><span class="sxs-lookup"><span data-stu-id="9605e-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="9605e-118">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9605e-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
