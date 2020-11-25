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
ms.openlocfilehash: 159ece09ae0b6a67780639da8aae8c0e4b412bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730700"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="8af27-102">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="8af27-102">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="8af27-103">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="8af27-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8af27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8af27-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8af27-105">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="8af27-106">enuncia Puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="8af27-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8af27-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8af27-107">Remarks</span></span>  

 <span data-ttu-id="8af27-108">El `GetSerializedBuffer` método serializa el objeto para que se puedan calcular las referencias del cliente.</span><span class="sxs-lookup"><span data-stu-id="8af27-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af27-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8af27-109">Requirements</span></span>  

 <span data-ttu-id="8af27-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af27-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af27-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8af27-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8af27-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8af27-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8af27-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af27-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af27-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8af27-114">See also</span></span>

- [<span data-ttu-id="8af27-115">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8af27-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
