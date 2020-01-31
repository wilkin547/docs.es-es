---
title: Interfaz ICorDebugComObjectValue
ms.date: 03/30/2017
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
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783972"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="1b361-102">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="1b361-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="1b361-103">Proporciona métodos para recuperar información asociada a un contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="1b361-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b361-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1b361-104">Methods</span></span>  
  
|<span data-ttu-id="1b361-105">Método</span><span class="sxs-lookup"><span data-stu-id="1b361-105">Method</span></span>|<span data-ttu-id="1b361-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b361-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b361-107">GetCachedInterfacePointers (método)</span><span class="sxs-lookup"><span data-stu-id="1b361-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="1b361-108">Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el RCW actual.</span><span class="sxs-lookup"><span data-stu-id="1b361-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="1b361-109">GetCachedInterfaceTypes (método)</span><span class="sxs-lookup"><span data-stu-id="1b361-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="1b361-110">Proporciona un enumerador para los tipos de interfaz en los que el objeto actual se ha usado como mayúsculas o minúsculas como.</span><span class="sxs-lookup"><span data-stu-id="1b361-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b361-111">Notas</span><span class="sxs-lookup"><span data-stu-id="1b361-111">Remarks</span></span>  
 <span data-ttu-id="1b361-112">Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un RCW, un depurador llama a `QueryInterface` de "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="1b361-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b361-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1b361-113">Requirements</span></span>  
 <span data-ttu-id="1b361-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b361-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b361-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b361-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b361-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b361-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b361-117">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b361-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b361-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b361-118">See also</span></span>

- [<span data-ttu-id="1b361-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1b361-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1b361-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="1b361-120">Debugging</span></span>](index.md)
