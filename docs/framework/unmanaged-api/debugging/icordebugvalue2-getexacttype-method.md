---
description: 'Más información sobre: ICorDebugValue2:: GetExactType ((método)'
title: ICorDebugValue2::GetExactType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: d0ef08b119106ced89ec2094b5bf67d0c874b6bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690315"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="f0550-103">ICorDebugValue2::GetExactType (Método)</span><span class="sxs-lookup"><span data-stu-id="f0550-103">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="f0550-104">Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.</span><span class="sxs-lookup"><span data-stu-id="f0550-104">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0550-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0550-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0550-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0550-106">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="f0550-107">enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="f0550-107">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0550-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0550-108">Remarks</span></span>  

 <span data-ttu-id="f0550-109">El método compatible con genéricos `GetExactType` sustituye a los métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , cada uno de los cuales devuelve información sobre el tipo de un valor.</span><span class="sxs-lookup"><span data-stu-id="f0550-109">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0550-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0550-110">Requirements</span></span>  

 <span data-ttu-id="f0550-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0550-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0550-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0550-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0550-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0550-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0550-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0550-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0550-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0550-115">See also</span></span>
