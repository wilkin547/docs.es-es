---
title: ILCodeKind (enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 553a92812f009ca1033f1bdcda0ea3722c5f01e3
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937833"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="e0e56-102">ILCodeKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="e0e56-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="e0e56-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e0e56-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e0e56-104">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e0e56-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e56-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0e56-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="e0e56-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="e0e56-106">Members</span></span>  
  
|<span data-ttu-id="e0e56-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="e0e56-107">Member name</span></span>|<span data-ttu-id="e0e56-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0e56-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="e0e56-109">El depurador no tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="e0e56-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="e0e56-110">El depurador tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="e0e56-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0e56-111">Notas</span><span class="sxs-lookup"><span data-stu-id="e0e56-111">Remarks</span></span>  
 <span data-ttu-id="e0e56-112">Un miembro de la enumeración `ILCodeKind` se puede pasar a los métodos [enumeratelocalvariablesex (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) y [getlocalvariableex (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) para determinar si el depurador puede acceder a las variables agregadas en la instrumentación ReJIT del generador de perfiles y al método [getcodeex (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) para determinar si el depurador puede tener acceso al Il instrumentado.</span><span class="sxs-lookup"><span data-stu-id="e0e56-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e56-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e0e56-113">Requirements</span></span>  
 <span data-ttu-id="e0e56-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0e56-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e56-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0e56-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0e56-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0e56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0e56-117">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e56-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0e56-118">See also</span></span>

- [<span data-ttu-id="e0e56-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e0e56-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="e0e56-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0e56-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="e0e56-121">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="e0e56-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
