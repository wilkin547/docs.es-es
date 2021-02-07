---
description: 'Más información sobre: Icordebugvalue3 (:: Getsize64 ((método)'
title: ICorDebugValue3::GetSize64 (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: ce7db5211c6a8fc16b58e0197fa3142b5b744d96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690202"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="fc4a8-103">ICorDebugValue3::GetSize64 (Método)</span><span class="sxs-lookup"><span data-stu-id="fc4a8-103">ICorDebugValue3::GetSize64 Method</span></span>

<span data-ttu-id="fc4a8-104">Obtiene el tamaño, en bytes, de este objeto [icordebugvalue3 (](icordebugvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fc4a8-104">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc4a8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc4a8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc4a8-106">Parameters</span></span>  

 <span data-ttu-id="fc4a8-107">pSize</span><span class="sxs-lookup"><span data-stu-id="fc4a8-107">pSize</span></span>  
 <span data-ttu-id="fc4a8-108">enuncia Puntero al tamaño, en bytes, de este objeto.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-108">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc4a8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fc4a8-109">Remarks</span></span>  

 <span data-ttu-id="fc4a8-110">Si el tipo de este valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-110">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="fc4a8-111">El `ICorDebugValue3::GetSize` método difiere del método [ICorDebugValue::](icordebugvalue-getsize-method.md) typeof en el tipo de su parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-111">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="fc4a8-112">En [ICorDebugValue:: obtiene](icordebugvalue-getsize-method.md), el parámetro de salida es un `ULONG32` ; en `ICorDebugValue3::GetSize` , es un `ULONG64` .</span><span class="sxs-lookup"><span data-stu-id="fc4a8-112">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="fc4a8-113">Esto permite a la interfaz [icordebugvalue3 (](icordebugvalue3-interface.md) informar del tamaño de las matrices que superan los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-113">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc4a8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc4a8-114">Requirements</span></span>  

 <span data-ttu-id="fc4a8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc4a8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc4a8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc4a8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc4a8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc4a8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc4a8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc4a8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc4a8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc4a8-119">See also</span></span>

- [<span data-ttu-id="fc4a8-120">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc4a8-120">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="fc4a8-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fc4a8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
