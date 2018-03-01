---
title: ICorDebugGuidToTypeEnum (Interfaz)
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
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9993a5aaaef3d5b83d21e3641029af12119188da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="24623-102">ICorDebugGuidToTypeEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24623-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="24623-103">Proporciona un enumerador que define la asignación entre un conjunto de GUID y sus tipos correspondientes, que están representados por instancias ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="24623-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="24623-104">Esta interfaz hereda los métodos de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="24623-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24623-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="24623-105">Methods</span></span>  
  
|<span data-ttu-id="24623-106">Método</span><span class="sxs-lookup"><span data-stu-id="24623-106">Method</span></span>|<span data-ttu-id="24623-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="24623-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24623-108">Icordebugguidtotypeenum:: Next</span><span class="sxs-lookup"><span data-stu-id="24623-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="24623-109">Obtiene el número especificado de [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instancias que se asignan los GUID para escribir información.</span><span class="sxs-lookup"><span data-stu-id="24623-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24623-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24623-110">Remarks</span></span>  
 <span data-ttu-id="24623-111">Un `ICorDebugGuidToTypeEnum` objeto de interfaz se puede recuperar mediante una llamada a la [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="24623-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="24623-112">Un depurador puede llamar a esta interfaz [siguiente](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) método para recuperar [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) los objetos que representan asignaciones de administrar representaciones de [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos cargan en el dominio de aplicación que se utiliza para la llamada a la [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="24623-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24623-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24623-113">Requirements</span></span>  
 <span data-ttu-id="24623-114">**Plataformas:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24623-114">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="24623-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24623-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24623-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24623-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24623-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24623-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24623-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="24623-118">See Also</span></span>  
 [<span data-ttu-id="24623-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="24623-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
