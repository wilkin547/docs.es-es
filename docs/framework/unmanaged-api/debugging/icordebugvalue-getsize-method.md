---
title: ICorDebugValue::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a9ff2c94c98a5acc930d68e648b0ea577a82c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492314"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="3d8cf-102">ICorDebugValue::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="3d8cf-103">Obtiene el tamaño, en bytes, de este objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="3d8cf-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d8cf-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d8cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d8cf-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="3d8cf-106">[out] El tamaño, en bytes, de este objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d8cf-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d8cf-107">Remarks</span></span>  
 <span data-ttu-id="3d8cf-108">Si el tipo de valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="3d8cf-109">El `ICorDebugValue::GetSize` devuelve del método `COR_E_OVERFLOW` para objetos que son mayores de 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="3d8cf-110">Use la [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) método en su lugar para los objetos que son mayores de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d8cf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d8cf-111">Requirements</span></span>  
 <span data-ttu-id="3d8cf-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d8cf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d8cf-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d8cf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d8cf-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d8cf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d8cf-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d8cf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8cf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d8cf-116">See also</span></span>

- [<span data-ttu-id="3d8cf-117">GetSize64 (método)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
