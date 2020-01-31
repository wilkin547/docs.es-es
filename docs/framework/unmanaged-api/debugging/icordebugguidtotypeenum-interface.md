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
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794437"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="07afc-102">ICorDebugGuidToTypeEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07afc-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="07afc-103">Proporciona un enumerador que define la asignación entre un conjunto de GUID y sus tipos correspondientes, que están representados por instancias de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="07afc-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="07afc-104">Esta interfaz hereda los métodos de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="07afc-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07afc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="07afc-105">Methods</span></span>  
  
|<span data-ttu-id="07afc-106">Método</span><span class="sxs-lookup"><span data-stu-id="07afc-106">Method</span></span>|<span data-ttu-id="07afc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="07afc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07afc-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="07afc-108">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="07afc-109">Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.</span><span class="sxs-lookup"><span data-stu-id="07afc-109">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07afc-110">Notas</span><span class="sxs-lookup"><span data-stu-id="07afc-110">Remarks</span></span>  
 <span data-ttu-id="07afc-111">Un objeto de interfaz de `ICorDebugGuidToTypeEnum` se puede recuperar llamando al método [ICorDebugAppDomain3:: getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="07afc-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="07afc-112">Un depurador puede llamar al [siguiente](icordebugguidtotypeenum-next-method.md) método de la interfaz para recuperar objetos [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que representan asignaciones de representaciones administradas de Windows Runtime tipos cargados en el dominio de aplicación que se usa para la llamada al método [ICorDebugAppDomain3:: getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="07afc-112">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07afc-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="07afc-113">Requirements</span></span>  
 <span data-ttu-id="07afc-114">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="07afc-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="07afc-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07afc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07afc-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07afc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07afc-117">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07afc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07afc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="07afc-118">See also</span></span>

- [<span data-ttu-id="07afc-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="07afc-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
