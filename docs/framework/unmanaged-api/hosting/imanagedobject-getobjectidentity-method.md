---
title: IManagedObject::GetObjectIdentity (Método)
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fbc4abe55d59c3140c5c180d5844404e357e3a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586318"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="c1086-102">IManagedObject::GetObjectIdentity (Método)</span><span class="sxs-lookup"><span data-stu-id="c1086-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="c1086-103">Obtiene la identidad de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="c1086-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1086-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1086-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1086-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1086-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="c1086-106">[out] Un puntero al GUID del proceso en el que reside el objeto.</span><span class="sxs-lookup"><span data-stu-id="c1086-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="c1086-107">[out] Un puntero al identificador del objeto dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1086-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="c1086-108">[out] Puntero al índice del objeto en COM clásico v-table.</span><span class="sxs-lookup"><span data-stu-id="c1086-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1086-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1086-109">Remarks</span></span>  
 <span data-ttu-id="c1086-110">La identidad de un objeto administrado incluye el GUID de proceso, Id. del dominio de aplicación y el índice del objeto en COM clásico v-table.</span><span class="sxs-lookup"><span data-stu-id="c1086-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1086-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1086-111">Requirements</span></span>  
 <span data-ttu-id="c1086-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1086-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1086-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1086-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1086-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1086-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1086-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1086-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1086-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1086-116">See also</span></span>
- [<span data-ttu-id="c1086-117">IManagedObject (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1086-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
