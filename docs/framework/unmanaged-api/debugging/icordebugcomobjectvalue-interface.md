---
description: 'Más información acerca de: interfaz ICorDebugComObjectValue'
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
ms.openlocfilehash: 3c071c371ae6e330431630cfb1934b538d62efe6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710821"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="ae8c8-103">Interfaz ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="ae8c8-103">ICorDebugComObjectValue Interface</span></span>

<span data-ttu-id="ae8c8-104">Proporciona métodos para recuperar información asociada a un contenedor RCW (Runtime Callable wrapper).</span><span class="sxs-lookup"><span data-stu-id="ae8c8-104">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae8c8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ae8c8-105">Methods</span></span>  
  
|<span data-ttu-id="ae8c8-106">Método</span><span class="sxs-lookup"><span data-stu-id="ae8c8-106">Method</span></span>|<span data-ttu-id="ae8c8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae8c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae8c8-108">Método GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="ae8c8-108">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="ae8c8-109">Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el RCW actual.</span><span class="sxs-lookup"><span data-stu-id="ae8c8-109">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="ae8c8-110">Método GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="ae8c8-110">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="ae8c8-111">Proporciona un enumerador para los tipos de interfaz en los que el objeto actual se ha usado como mayúsculas o minúsculas como.</span><span class="sxs-lookup"><span data-stu-id="ae8c8-111">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae8c8-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ae8c8-112">Remarks</span></span>  

 <span data-ttu-id="ae8c8-113">Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un RCW, un depurador llama a `QueryInterface` "ICorDebugValue" con `IID_ICorDebugComObjectValue` .</span><span class="sxs-lookup"><span data-stu-id="ae8c8-113">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae8c8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae8c8-114">Requirements</span></span>  

 <span data-ttu-id="ae8c8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae8c8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae8c8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae8c8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae8c8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae8c8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae8c8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae8c8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8c8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae8c8-119">See also</span></span>

- [<span data-ttu-id="ae8c8-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ae8c8-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ae8c8-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="ae8c8-121">Debugging</span></span>](index.md)
