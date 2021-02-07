---
description: 'Más información sobre: IManagedObject:: GetObjectIdentity ((método)'
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
ms.openlocfilehash: 8929819bbf490680b5f3f1f47b9f3b8e830d57ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671170"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="324ea-103">IManagedObject::GetObjectIdentity (Método)</span><span class="sxs-lookup"><span data-stu-id="324ea-103">IManagedObject::GetObjectIdentity Method</span></span>

<span data-ttu-id="324ea-104">Obtiene la identidad de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="324ea-104">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="324ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="324ea-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="324ea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="324ea-106">Parameters</span></span>  

 `pBSTRGUID`  
 <span data-ttu-id="324ea-107">enuncia Puntero al GUID del proceso en el que reside el objeto.</span><span class="sxs-lookup"><span data-stu-id="324ea-107">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="324ea-108">enuncia Puntero al identificador del dominio de aplicación del objeto.</span><span class="sxs-lookup"><span data-stu-id="324ea-108">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="324ea-109">enuncia Puntero al índice de un objeto en la tabla v clásica de COM.</span><span class="sxs-lookup"><span data-stu-id="324ea-109">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="324ea-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="324ea-110">Remarks</span></span>  

 <span data-ttu-id="324ea-111">La identidad de un objeto administrado incluye el GUID del proceso, el identificador del dominio de aplicación y el índice del objeto en la tabla v clásica de COM.</span><span class="sxs-lookup"><span data-stu-id="324ea-111">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="324ea-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="324ea-112">Requirements</span></span>  

 <span data-ttu-id="324ea-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="324ea-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="324ea-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="324ea-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="324ea-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="324ea-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="324ea-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="324ea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="324ea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="324ea-117">See also</span></span>

- [<span data-ttu-id="324ea-118">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="324ea-118">IManagedObject Interface</span></span>](imanagedobject-interface.md)
