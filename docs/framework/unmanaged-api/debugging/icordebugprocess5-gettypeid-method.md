---
title: "ICorDebugProcess5::GetTypeID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugProcess5.GetTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15ee5c4e3c3f299e24f7bdbed20654e3d4d7e997
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="476a0-102">ICorDebugProcess5::GetTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="476a0-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="476a0-103">Convierte una dirección de objeto a una [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identificador.</span><span class="sxs-lookup"><span data-stu-id="476a0-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="476a0-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="476a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="476a0-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="476a0-106">[in] La dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="476a0-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="476a0-107">Un puntero a la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el objeto.</span><span class="sxs-lookup"><span data-stu-id="476a0-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="476a0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="476a0-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="476a0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="476a0-109">Requirements</span></span>  
 <span data-ttu-id="476a0-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="476a0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="476a0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="476a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="476a0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="476a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="476a0-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="476a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="476a0-114">See Also</span></span>  
 [<span data-ttu-id="476a0-115">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="476a0-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="476a0-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="476a0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
