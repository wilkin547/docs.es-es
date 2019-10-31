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
ms.openlocfilehash: 4a55ae265230c4da3cc0a19b06a7597be8661beb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103246"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="9bf75-102">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="9bf75-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="9bf75-103">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="9bf75-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bf75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bf75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9bf75-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="9bf75-106">enuncia Puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="9bf75-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bf75-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bf75-107">Remarks</span></span>  
 <span data-ttu-id="9bf75-108">El método `GetSerializedBuffer` serializa el objeto para que se puedan calcular las referencias del cliente.</span><span class="sxs-lookup"><span data-stu-id="9bf75-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf75-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9bf75-109">Requirements</span></span>  
 <span data-ttu-id="9bf75-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bf75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf75-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9bf75-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9bf75-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9bf75-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bf75-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf75-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bf75-114">See also</span></span>

- [<span data-ttu-id="9bf75-115">IManagedObject (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9bf75-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
