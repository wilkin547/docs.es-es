---
title: Interfaz ICorDebugType2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d44514586a2e91dad3486b6dc04c26946148885
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="3ea53-102">Interfaz ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="3ea53-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="3ea53-103">Extiende la interfaz ICorDebugType para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="3ea53-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ea53-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3ea53-104">Methods</span></span>  
  
|<span data-ttu-id="3ea53-105">Método</span><span class="sxs-lookup"><span data-stu-id="3ea53-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="3ea53-106">GetTypeID (método)</span><span class="sxs-lookup"><span data-stu-id="3ea53-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="3ea53-107">Obtiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para este tipo.</span><span class="sxs-lookup"><span data-stu-id="3ea53-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ea53-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ea53-108">Remarks</span></span>  
 <span data-ttu-id="3ea53-109">Esta interfaz es una extensión lógica de ICorDebugType (interfaz).</span><span class="sxs-lookup"><span data-stu-id="3ea53-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ea53-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3ea53-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ea53-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ea53-111">Example</span></span>  
 <span data-ttu-id="3ea53-112">El siguiente fragmento de código muestra el uso de la [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3ea53-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="3ea53-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ea53-113">Requirements</span></span>  
 <span data-ttu-id="3ea53-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ea53-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ea53-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ea53-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ea53-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ea53-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ea53-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ea53-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea53-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ea53-118">See Also</span></span>  
 [<span data-ttu-id="3ea53-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3ea53-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
