---
description: 'Más información acerca de: ICorDebugValue:: GetAddress (método)'
title: ICorDebugValue::GetAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: c922388fbab820e50edffc140be94a2c0920099d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690436"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="3f4d3-103">ICorDebugValue::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="3f4d3-103">ICorDebugValue::GetAddress Method</span></span>

<span data-ttu-id="3f4d3-104">Obtiene la dirección de este objeto "ICorDebugValue", que está en proceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="3f4d3-104">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4d3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f4d3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f4d3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f4d3-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="3f4d3-107">enuncia Puntero a un `CORDB_ADDRESS` objeto que especifica la dirección de este objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="3f4d3-107">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f4d3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f4d3-108">Remarks</span></span>  

 <span data-ttu-id="3f4d3-109">Si el valor no está disponible, se devuelve 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="3f4d3-109">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="3f4d3-110">Esto puede ocurrir si el valor es, al menos, parcialmente en registros o almacenados en un identificador de recolector de elementos no utilizados ( `GCHandle` ).</span><span class="sxs-lookup"><span data-stu-id="3f4d3-110">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4d3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f4d3-111">Requirements</span></span>  

 <span data-ttu-id="3f4d3-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f4d3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f4d3-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f4d3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f4d3-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f4d3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f4d3-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4d3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f4d3-116">See also</span></span>
