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
ms.openlocfilehash: 1b40ed8e107d30c22b4ade25d29376b1b74583d1
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842418"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="04387-102">IManagedObject::GetObjectIdentity (Método)</span><span class="sxs-lookup"><span data-stu-id="04387-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="04387-103">Obtiene la identidad de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="04387-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04387-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04387-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04387-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04387-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="04387-106">enuncia Puntero al GUID del proceso en el que reside el objeto.</span><span class="sxs-lookup"><span data-stu-id="04387-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="04387-107">enuncia Puntero al identificador del dominio de aplicación del objeto.</span><span class="sxs-lookup"><span data-stu-id="04387-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="04387-108">enuncia Puntero al índice de un objeto en la tabla v clásica de COM.</span><span class="sxs-lookup"><span data-stu-id="04387-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04387-109">Notas</span><span class="sxs-lookup"><span data-stu-id="04387-109">Remarks</span></span>  
 <span data-ttu-id="04387-110">La identidad de un objeto administrado incluye el GUID del proceso, el identificador del dominio de aplicación y el índice del objeto en la tabla v clásica de COM.</span><span class="sxs-lookup"><span data-stu-id="04387-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04387-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04387-111">Requirements</span></span>  
 <span data-ttu-id="04387-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04387-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04387-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04387-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04387-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04387-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04387-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04387-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04387-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="04387-116">See also</span></span>

- [<span data-ttu-id="04387-117">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04387-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
