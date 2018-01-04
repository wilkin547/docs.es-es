---
title: "ILCodeKind (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ILCodeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a79444fe379d6147895e89b25e513b7f4ac7a0ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="76ea3-102">ILCodeKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="76ea3-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="76ea3-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="76ea3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="76ea3-104">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="76ea3-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ea3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76ea3-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="76ea3-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="76ea3-106">Members</span></span>  
  
|<span data-ttu-id="76ea3-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="76ea3-107">Member name</span></span>|<span data-ttu-id="76ea3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="76ea3-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="76ea3-109">El depurador no tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="76ea3-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="76ea3-110">El depurador tiene acceso a la información de la instrumentación ReJIT.</span><span class="sxs-lookup"><span data-stu-id="76ea3-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ea3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76ea3-111">Remarks</span></span>  
 <span data-ttu-id="76ea3-112">Un miembro de la `ILCodeKind` enumeración puede pasarse a la [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) y [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) métodos para determinar si el depurador puede tener acceso a las variables agregadas en el generador de perfiles La instrumentación ReJIT y a la [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) método para determinar si el depurador puede acceder al IL instrumentado.</span><span class="sxs-lookup"><span data-stu-id="76ea3-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ea3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76ea3-113">Requirements</span></span>  
 <span data-ttu-id="76ea3-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ea3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ea3-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76ea3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76ea3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76ea3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ea3-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ea3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ea3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="76ea3-118">See Also</span></span>  
 [<span data-ttu-id="76ea3-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="76ea3-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="76ea3-120">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76ea3-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="76ea3-121">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="76ea3-121">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
