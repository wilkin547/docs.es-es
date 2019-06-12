---
title: ICorDebugGuidToTypeEnum (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22cd08154268bdf1e819a0ec0067b05a81d60b22
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025824"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="d0e09-102">ICorDebugGuidToTypeEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0e09-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="d0e09-103">Proporciona un enumerador que define la asignación entre un conjunto de GUID y sus tipos correspondientes, que se representan mediante instancias de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="d0e09-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="d0e09-104">Esta interfaz hereda los métodos de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="d0e09-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0e09-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d0e09-105">Methods</span></span>  
  
|<span data-ttu-id="d0e09-106">Método</span><span class="sxs-lookup"><span data-stu-id="d0e09-106">Method</span></span>|<span data-ttu-id="d0e09-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0e09-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0e09-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="d0e09-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="d0e09-109">Obtiene el número especificado de [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instancias que se asignan los GUID para escribir información.</span><span class="sxs-lookup"><span data-stu-id="d0e09-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e09-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0e09-110">Remarks</span></span>  
 <span data-ttu-id="d0e09-111">Un `ICorDebugGuidToTypeEnum` el objeto de interfaz se puede recuperar mediante una llamada a la [Icordebugappdomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d0e09-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="d0e09-112">Un depurador puede llamar a esta interfaz [siguiente](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) método para recuperar [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) los objetos que representan las asignaciones de representaciones de tipos en tiempo de ejecución de Windows administradas se cargan en el dominio de aplicación utilizado para la llamada a la [Icordebugappdomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d0e09-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0e09-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0e09-113">Requirements</span></span>  
 <span data-ttu-id="d0e09-114">**Plataformas:** Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d0e09-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="d0e09-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0e09-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0e09-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0e09-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0e09-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0e09-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e09-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0e09-118">See also</span></span>

- [<span data-ttu-id="d0e09-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d0e09-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
