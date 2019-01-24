---
title: ICorDebugProcess5::GetTypeID (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cf72d0f41ee916db0e65cc6799217d19893628b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597104"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="4f794-102">ICorDebugProcess5::GetTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="4f794-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="4f794-103">Convierte una dirección de objeto a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identificador.</span><span class="sxs-lookup"><span data-stu-id="4f794-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f794-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f794-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f794-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f794-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="4f794-106">[in] La dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="4f794-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="4f794-107">Un puntero a la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el objeto.</span><span class="sxs-lookup"><span data-stu-id="4f794-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f794-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f794-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f794-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f794-109">Requirements</span></span>  
 <span data-ttu-id="4f794-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f794-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f794-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f794-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f794-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f794-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f794-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f794-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f794-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f794-114">See also</span></span>
- [<span data-ttu-id="4f794-115">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f794-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="4f794-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4f794-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
