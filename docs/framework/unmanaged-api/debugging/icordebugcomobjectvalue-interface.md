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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3387985ebf6027b9cd9dee372190da65939dbae3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098629"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="d554f-102">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="d554f-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="d554f-103">Proporciona métodos para recuperar la información asociada a un contenedor invocable en tiempo de ejecución (RCW).</span><span class="sxs-lookup"><span data-stu-id="d554f-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d554f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d554f-104">Methods</span></span>  
  
|<span data-ttu-id="d554f-105">Método</span><span class="sxs-lookup"><span data-stu-id="d554f-105">Method</span></span>|<span data-ttu-id="d554f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d554f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d554f-107">Método GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="d554f-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="d554f-108">Obtiene los punteros de interfaz sin formato almacenados en caché en el RCW actual.</span><span class="sxs-lookup"><span data-stu-id="d554f-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="d554f-109">Método GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="d554f-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="d554f-110">Proporciona un enumerador para los tipos de interfaz que el objeto actual se ha convertido en grafía o usar como.</span><span class="sxs-lookup"><span data-stu-id="d554f-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d554f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d554f-111">Remarks</span></span>  
 <span data-ttu-id="d554f-112">Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un contenedor RCW, llama un depurador `QueryInterface` en "ICorDebugValue" con `IID_ICorDebugComObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="d554f-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d554f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d554f-113">Requirements</span></span>  
 <span data-ttu-id="d554f-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d554f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d554f-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d554f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d554f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d554f-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d554f-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d554f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d554f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d554f-118">See also</span></span>

- [<span data-ttu-id="d554f-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d554f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d554f-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="d554f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
