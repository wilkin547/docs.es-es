---
title: ILCodeKind (Enumeración)
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
ms.openlocfilehash: 0586b9e184a0958b978837601db002e035881cbc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421038"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="73159-102">ILCodeKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="73159-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="73159-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="73159-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="73159-104">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="73159-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73159-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73159-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="73159-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="73159-106">Members</span></span>  
  
|<span data-ttu-id="73159-107">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="73159-107">Member name</span></span>|<span data-ttu-id="73159-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="73159-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="73159-109">El depurador no tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="73159-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="73159-110">El depurador tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="73159-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73159-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73159-111">Remarks</span></span>  
 <span data-ttu-id="73159-112">Un miembro de la `ILCodeKind` enumeración se puede pasar a los métodos [Enumeratelocalvariablesex (](icordebugilframe4-enumeratelocalvariablesex-method.md) y [getlocalvariableex (](icordebugilframe4-getlocalvariableex-method.md) para determinar si el depurador puede tener acceso a las variables agregadas en la instrumentación ReJIT del generador de perfiles y al método [getcodeex (](icordebugilframe4-getcodeex-method.md) para determinar si el depurador puede tener acceso al Il instrumentado.</span><span class="sxs-lookup"><span data-stu-id="73159-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73159-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73159-113">Requirements</span></span>  
 <span data-ttu-id="73159-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73159-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73159-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73159-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73159-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73159-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73159-117">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73159-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73159-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="73159-118">See also</span></span>

- [<span data-ttu-id="73159-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="73159-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="73159-120">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73159-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="73159-121">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="73159-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
