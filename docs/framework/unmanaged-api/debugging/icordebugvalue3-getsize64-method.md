---
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
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791098"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="c4179-102">ICorDebugValue3::GetSize64 (Método)</span><span class="sxs-lookup"><span data-stu-id="c4179-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="c4179-103">Obtiene el tamaño, en bytes, de este objeto [icordebugvalue3 (](icordebugvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c4179-103">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4179-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4179-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4179-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c4179-105">Parameters</span></span>  
 <span data-ttu-id="c4179-106">pSize</span><span class="sxs-lookup"><span data-stu-id="c4179-106">pSize</span></span>  
 <span data-ttu-id="c4179-107">enuncia Puntero al tamaño, en bytes, de este objeto.</span><span class="sxs-lookup"><span data-stu-id="c4179-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4179-108">Notas</span><span class="sxs-lookup"><span data-stu-id="c4179-108">Remarks</span></span>  
 <span data-ttu-id="c4179-109">Si el tipo de este valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="c4179-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="c4179-110">El método `ICorDebugValue3::GetSize` difiere del método [ICorDebugValue::](icordebugvalue-getsize-method.md) typeof en el tipo de su parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="c4179-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="c4179-111">En [ICorDebugValue:: obtiene](icordebugvalue-getsize-method.md), el parámetro de salida es un `ULONG32`; en `ICorDebugValue3::GetSize`, es un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="c4179-111">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="c4179-112">Esto permite a la interfaz [icordebugvalue3 (](icordebugvalue3-interface.md) informar del tamaño de las matrices que superan los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="c4179-112">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4179-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c4179-113">Requirements</span></span>  
 <span data-ttu-id="c4179-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4179-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4179-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4179-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4179-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4179-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4179-117">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4179-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4179-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4179-118">See also</span></span>

- [<span data-ttu-id="c4179-119">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4179-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="c4179-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c4179-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
