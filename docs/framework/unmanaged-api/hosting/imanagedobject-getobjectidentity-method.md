---
title: "IManagedObject::GetObjectIdentity (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IManagedObject.GetObjectIdentity
api_location: mscoree.dll
api_type: COM
f1_keywords: GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5654865c557e6e004685f66753366d7cb575919
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="5d9b9-102">IManagedObject::GetObjectIdentity (Método)</span><span class="sxs-lookup"><span data-stu-id="5d9b9-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="5d9b9-103">Obtiene la identidad de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d9b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d9b9-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d9b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d9b9-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="5d9b9-106">[out] Un puntero al GUID del proceso en el que reside el objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="5d9b9-107">[out] Un puntero al identificador del objeto dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="5d9b9-108">[out] Puntero al índice del objeto en COM clásico v-table.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d9b9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d9b9-109">Remarks</span></span>  
 <span data-ttu-id="5d9b9-110">La identidad de un objeto administrado incluye el GUID de proceso, Id. de dominio de aplicación y el índice del objeto en COM clásico v-table.</span><span class="sxs-lookup"><span data-stu-id="5d9b9-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d9b9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d9b9-111">Requirements</span></span>  
 <span data-ttu-id="5d9b9-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d9b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d9b9-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d9b9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d9b9-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d9b9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d9b9-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d9b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9b9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d9b9-116">See Also</span></span>  
 [<span data-ttu-id="5d9b9-117">IManagedObject (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d9b9-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
