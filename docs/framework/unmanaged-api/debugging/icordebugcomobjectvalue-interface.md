---
title: Interfaz ICorDebugComObjectValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9adeec14e102ef575f24566980477a285f87ba40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="52518-102">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="52518-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="52518-103">Proporciona métodos para recuperar la información asociada a un contenedor invocable en tiempo de ejecución (RCW).</span><span class="sxs-lookup"><span data-stu-id="52518-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52518-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="52518-104">Methods</span></span>  
  
|<span data-ttu-id="52518-105">Método</span><span class="sxs-lookup"><span data-stu-id="52518-105">Method</span></span>|<span data-ttu-id="52518-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="52518-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52518-107">GetCachedInterfacePointers (método)</span><span class="sxs-lookup"><span data-stu-id="52518-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="52518-108">Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el contenedor RCW actual.</span><span class="sxs-lookup"><span data-stu-id="52518-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="52518-109">GetCachedInterfaceTypes (método)</span><span class="sxs-lookup"><span data-stu-id="52518-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="52518-110">Proporciona un enumerador para los tipos de interfaz que el objeto actual se ha a las mayúsculas y minúsculas o usar como.</span><span class="sxs-lookup"><span data-stu-id="52518-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52518-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52518-111">Remarks</span></span>  
 <span data-ttu-id="52518-112">Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un RCW, llama a un depurador `QueryInterface` en "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="52518-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52518-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52518-113">Requirements</span></span>  
 <span data-ttu-id="52518-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52518-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52518-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52518-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52518-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52518-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52518-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52518-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52518-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="52518-118">See Also</span></span>  
 [<span data-ttu-id="52518-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="52518-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="52518-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="52518-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
