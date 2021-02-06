---
description: 'Más información acerca de: interfaz Icordebugguidtotypeenum ('
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
ms.openlocfilehash: abcdc9537f6f6ff2e0ac9b2be86734efbf303493
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660991"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="466d4-103">ICorDebugGuidToTypeEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="466d4-103">ICorDebugGuidToTypeEnum Interface</span></span>

<span data-ttu-id="466d4-104">Proporciona un enumerador que define la asignación entre un conjunto de GUID y sus tipos correspondientes, que están representados por instancias de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="466d4-104">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="466d4-105">Esta interfaz hereda los métodos de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="466d4-105">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="466d4-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="466d4-106">Methods</span></span>  
  
|<span data-ttu-id="466d4-107">Método</span><span class="sxs-lookup"><span data-stu-id="466d4-107">Method</span></span>|<span data-ttu-id="466d4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="466d4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="466d4-109">Icordebugguidtotypeenum (:: Next</span><span class="sxs-lookup"><span data-stu-id="466d4-109">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="466d4-110">Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.</span><span class="sxs-lookup"><span data-stu-id="466d4-110">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="466d4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="466d4-111">Remarks</span></span>  

 <span data-ttu-id="466d4-112">Un `ICorDebugGuidToTypeEnum` objeto de interfaz se puede recuperar llamando al método [ICorDebugAppDomain3:: getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="466d4-112">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="466d4-113">Un depurador puede llamar al [siguiente](icordebugguidtotypeenum-next-method.md) método de la interfaz para recuperar objetos [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que representan asignaciones de representaciones administradas de Windows Runtime tipos cargados en el dominio de aplicación que se usa para la llamada al método [ICorDebugAppDomain3:: getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="466d4-113">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="466d4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="466d4-114">Requirements</span></span>  

 <span data-ttu-id="466d4-115">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="466d4-115">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="466d4-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="466d4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="466d4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="466d4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="466d4-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466d4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466d4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="466d4-119">See also</span></span>

- [<span data-ttu-id="466d4-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="466d4-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
