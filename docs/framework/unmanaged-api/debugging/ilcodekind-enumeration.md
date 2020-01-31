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
ms.openlocfilehash: 20e2e3f177b12221832786f4fab86635098d1989
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790487"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="81507-102">ILCodeKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="81507-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="81507-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="81507-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="81507-104">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="81507-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81507-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81507-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="81507-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="81507-106">Members</span></span>  
  
|<span data-ttu-id="81507-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="81507-107">Member name</span></span>|<span data-ttu-id="81507-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="81507-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="81507-109">El depurador no tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="81507-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="81507-110">El depurador tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="81507-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81507-111">Notas</span><span class="sxs-lookup"><span data-stu-id="81507-111">Remarks</span></span>  
 <span data-ttu-id="81507-112">Un miembro de la enumeración `ILCodeKind` se puede pasar a los métodos [enumeratelocalvariablesex (](icordebugilframe4-enumeratelocalvariablesex-method.md) y [getlocalvariableex (](icordebugilframe4-getlocalvariableex-method.md) para determinar si el depurador puede acceder a las variables agregadas en la instrumentación ReJIT del generador de perfiles y al método [getcodeex (](icordebugilframe4-getcodeex-method.md) para determinar si el depurador puede tener acceso al Il instrumentado.</span><span class="sxs-lookup"><span data-stu-id="81507-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81507-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="81507-113">Requirements</span></span>  
 <span data-ttu-id="81507-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81507-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81507-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81507-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81507-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81507-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81507-117">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81507-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81507-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="81507-118">See also</span></span>

- [<span data-ttu-id="81507-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="81507-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="81507-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="81507-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="81507-121">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="81507-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
