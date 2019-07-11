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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96e63d121bb64fd1aa6433881f7806b5c4058115
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774004"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="0fa20-102">ICorDebugValue3::GetSize64 (Método)</span><span class="sxs-lookup"><span data-stu-id="0fa20-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="0fa20-103">Obtiene el tamaño, en bytes, de este [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="0fa20-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fa20-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fa20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fa20-105">Parameters</span></span>  
 <span data-ttu-id="0fa20-106">pSize</span><span class="sxs-lookup"><span data-stu-id="0fa20-106">pSize</span></span>  
 <span data-ttu-id="0fa20-107">[out] Un puntero al tamaño, en bytes, de este objeto.</span><span class="sxs-lookup"><span data-stu-id="0fa20-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fa20-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fa20-108">Remarks</span></span>  
 <span data-ttu-id="0fa20-109">Si el tipo de este valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="0fa20-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="0fa20-110">El `ICorDebugValue3::GetSize` método difiere el [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) método en el tipo de su parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="0fa20-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="0fa20-111">En [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), el parámetro de salida es un `ULONG32`; en `ICorDebugValue3::GetSize`, es un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="0fa20-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="0fa20-112">Esto permite la [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interfaz para notificar el tamaño de matrices que superan los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="0fa20-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fa20-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fa20-113">Requirements</span></span>  
 <span data-ttu-id="0fa20-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fa20-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa20-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fa20-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fa20-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fa20-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fa20-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa20-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa20-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fa20-118">See also</span></span>

- [<span data-ttu-id="0fa20-119">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fa20-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="0fa20-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0fa20-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
