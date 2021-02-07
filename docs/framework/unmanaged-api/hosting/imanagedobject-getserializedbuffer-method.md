---
description: 'Más información sobre: IManagedObject:: Getserializedbuffer ((método)'
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
ms.openlocfilehash: f324b6ed1e9cea21fec9027a954fbad54174dd0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753775"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="3cdf0-103">IManagedObject::GetSerializedBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="3cdf0-103">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="3cdf0-104">Obtiene la representación de cadena de este objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="3cdf0-104">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdf0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cdf0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cdf0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cdf0-106">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="3cdf0-107">enuncia Puntero a una cadena que es el objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="3cdf0-107">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cdf0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3cdf0-108">Remarks</span></span>  

 <span data-ttu-id="3cdf0-109">El `GetSerializedBuffer` método serializa el objeto para que se puedan calcular las referencias del cliente.</span><span class="sxs-lookup"><span data-stu-id="3cdf0-109">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cdf0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cdf0-110">Requirements</span></span>  

 <span data-ttu-id="3cdf0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cdf0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cdf0-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3cdf0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cdf0-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cdf0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cdf0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cdf0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdf0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cdf0-115">See also</span></span>

- [<span data-ttu-id="3cdf0-116">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cdf0-116">IManagedObject Interface</span></span>](imanagedobject-interface.md)
