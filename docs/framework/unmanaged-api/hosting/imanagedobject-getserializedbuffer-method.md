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
ms.openlocfilehash: cb9242160b684b3c7b90756d7b20811ad162fc30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156148"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="38ad7-102">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="38ad7-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="38ad7-103">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="38ad7-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ad7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38ad7-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ad7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38ad7-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="38ad7-106">[out] Un puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="38ad7-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38ad7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38ad7-107">Remarks</span></span>  
 <span data-ttu-id="38ad7-108">El `GetSerializedBuffer` método serializa el objeto, por lo que se pueden calcular las referencias al cliente.</span><span class="sxs-lookup"><span data-stu-id="38ad7-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ad7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38ad7-109">Requirements</span></span>  
 <span data-ttu-id="38ad7-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38ad7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38ad7-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38ad7-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38ad7-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38ad7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="38ad7-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="38ad7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38ad7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="38ad7-114">See also</span></span>

- [<span data-ttu-id="38ad7-115">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="38ad7-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
