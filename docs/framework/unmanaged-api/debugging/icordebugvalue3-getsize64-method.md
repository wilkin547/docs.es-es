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
ms.openlocfilehash: c5d3925741e9777e4fcd1752d8e24bf71ad1579f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422642"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="cff9e-102">ICorDebugValue3::GetSize64 (Método)</span><span class="sxs-lookup"><span data-stu-id="cff9e-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="cff9e-103">Obtiene el tamaño, en bytes, de este [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="cff9e-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff9e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cff9e-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cff9e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cff9e-105">Parameters</span></span>  
 <span data-ttu-id="cff9e-106">pSize</span><span class="sxs-lookup"><span data-stu-id="cff9e-106">pSize</span></span>  
 <span data-ttu-id="cff9e-107">[out] Un puntero al tamaño, en bytes, de este objeto.</span><span class="sxs-lookup"><span data-stu-id="cff9e-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cff9e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cff9e-108">Remarks</span></span>  
 <span data-ttu-id="cff9e-109">Si el tipo de este valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar de con el tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="cff9e-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="cff9e-110">El `ICorDebugValue3::GetSize` método difiere de la [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) método en el tipo del parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="cff9e-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="cff9e-111">En [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), el parámetro de salida es un `ULONG32`; en `ICorDebugValue3::GetSize`, es un `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="cff9e-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="cff9e-112">Esto permite la [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interfaz para notificar el tamaño de las matrices que superan los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="cff9e-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff9e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cff9e-113">Requirements</span></span>  
 <span data-ttu-id="cff9e-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cff9e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff9e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cff9e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cff9e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cff9e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cff9e-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff9e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff9e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cff9e-118">See Also</span></span>  
 [<span data-ttu-id="cff9e-119">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cff9e-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="cff9e-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cff9e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
