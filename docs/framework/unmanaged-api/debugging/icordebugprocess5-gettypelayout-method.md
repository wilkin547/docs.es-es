---
title: "ICorDebugProcess5::GetTypeLayout (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeLayout
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4317fd374646dd5187a94f3e91cc88df939ed762
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="32826-102">ICorDebugProcess5::GetTypeLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="32826-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="32826-103">Obtiene información sobre el diseño de un objeto en la memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="32826-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32826-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32826-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32826-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32826-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="32826-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) símbolo (token) que especifica el tipo cuyo diseño se desea.</span><span class="sxs-lookup"><span data-stu-id="32826-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="32826-107">[out] Un puntero a un [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) estructura que contiene información sobre el diseño del objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="32826-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32826-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32826-108">Remarks</span></span>  
 <span data-ttu-id="32826-109">El `ICorDebugProcess5::GetTypeLayout` método proporciona información acerca de un objeto basado en su [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), que devuelve un número de otros [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="32826-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="32826-110">La información se proporciona mediante un [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) estructura que se rellena con el método.</span><span class="sxs-lookup"><span data-stu-id="32826-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32826-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32826-111">Requirements</span></span>  
 <span data-ttu-id="32826-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32826-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32826-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32826-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32826-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32826-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32826-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32826-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32826-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="32826-116">See Also</span></span>  
 [<span data-ttu-id="32826-117">COR_TYPE_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="32826-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [<span data-ttu-id="32826-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32826-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="32826-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="32826-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
