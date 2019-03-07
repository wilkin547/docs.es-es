---
title: IManagedObject::GetSerializedBuffer (Método)
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7930e993640e1ae88ce65b6c2025a5b62a0d0999
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502467"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="88c82-102">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="88c82-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="88c82-103">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="88c82-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88c82-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88c82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88c82-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="88c82-106">[out] Un puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="88c82-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88c82-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88c82-107">Remarks</span></span>  
 <span data-ttu-id="88c82-108">El `GetSerializedBuffer` método serializa el objeto, por lo que se pueden calcular las referencias al cliente.</span><span class="sxs-lookup"><span data-stu-id="88c82-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88c82-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88c82-109">Requirements</span></span>  
 <span data-ttu-id="88c82-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88c82-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88c82-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88c82-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88c82-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88c82-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88c82-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88c82-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c82-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="88c82-114">See also</span></span>
- [<span data-ttu-id="88c82-115">IManagedObject (interfaz)</span><span class="sxs-lookup"><span data-stu-id="88c82-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
