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
ms.openlocfilehash: c68ec0b41bb38afc7cefaf47df718fffcf42d250
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842436"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="c00a3-102">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="c00a3-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="c00a3-103">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="c00a3-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c00a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c00a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c00a3-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="c00a3-106">enuncia Puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="c00a3-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c00a3-107">Notas</span><span class="sxs-lookup"><span data-stu-id="c00a3-107">Remarks</span></span>  
 <span data-ttu-id="c00a3-108">El `GetSerializedBuffer` método serializa el objeto para que se puedan calcular las referencias del cliente.</span><span class="sxs-lookup"><span data-stu-id="c00a3-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00a3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c00a3-109">Requirements</span></span>  
 <span data-ttu-id="c00a3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c00a3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00a3-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c00a3-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c00a3-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c00a3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c00a3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00a3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c00a3-114">See also</span></span>

- [<span data-ttu-id="c00a3-115">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c00a3-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
