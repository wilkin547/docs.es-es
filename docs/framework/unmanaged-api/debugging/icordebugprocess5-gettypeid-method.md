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
ms.openlocfilehash: 07c23a32037e83a878bb3136c48176f19249b207
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173193"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="2676e-102">ICorDebugProcess5::GetTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="2676e-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="2676e-103">Convierte una dirección de objeto a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identificador.</span><span class="sxs-lookup"><span data-stu-id="2676e-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2676e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2676e-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2676e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2676e-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="2676e-106">[in] La dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="2676e-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="2676e-107">Un puntero a la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el objeto.</span><span class="sxs-lookup"><span data-stu-id="2676e-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2676e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2676e-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2676e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2676e-109">Requirements</span></span>  
 <span data-ttu-id="2676e-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2676e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2676e-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2676e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2676e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2676e-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2676e-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2676e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2676e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2676e-114">See also</span></span>

- [<span data-ttu-id="2676e-115">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2676e-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="2676e-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2676e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
