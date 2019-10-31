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
ms.openlocfilehash: 4ff5c0d470e6eb84eb8b526f5e8f74e5e1a8118a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125487"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="da8fa-102">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="da8fa-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="da8fa-103">Proporciona métodos para recuperar información asociada a un contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="da8fa-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da8fa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="da8fa-104">Methods</span></span>  
  
|<span data-ttu-id="da8fa-105">Método</span><span class="sxs-lookup"><span data-stu-id="da8fa-105">Method</span></span>|<span data-ttu-id="da8fa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="da8fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da8fa-107">GetCachedInterfacePointers (método)</span><span class="sxs-lookup"><span data-stu-id="da8fa-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="da8fa-108">Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el RCW actual.</span><span class="sxs-lookup"><span data-stu-id="da8fa-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="da8fa-109">GetCachedInterfaceTypes (método)</span><span class="sxs-lookup"><span data-stu-id="da8fa-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="da8fa-110">Proporciona un enumerador para los tipos de interfaz en los que el objeto actual se ha usado como mayúsculas o minúsculas como.</span><span class="sxs-lookup"><span data-stu-id="da8fa-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da8fa-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da8fa-111">Remarks</span></span>  
 <span data-ttu-id="da8fa-112">Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un RCW, un depurador llama a `QueryInterface` de "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="da8fa-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da8fa-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da8fa-113">Requirements</span></span>  
 <span data-ttu-id="da8fa-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da8fa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da8fa-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da8fa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da8fa-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da8fa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da8fa-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da8fa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8fa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="da8fa-118">See also</span></span>

- [<span data-ttu-id="da8fa-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="da8fa-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="da8fa-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="da8fa-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
