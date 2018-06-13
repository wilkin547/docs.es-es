---
title: WriteableMetadataUpdateMode (Enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fbf9a24c350dd4c33bb50b0add8817c8922925f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436012"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="5faf2-102">WriteableMetadataUpdateMode (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5faf2-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="5faf2-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="5faf2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5faf2-104">Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.</span><span class="sxs-lookup"><span data-stu-id="5faf2-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5faf2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5faf2-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="5faf2-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="5faf2-106">Members</span></span>  
  
|<span data-ttu-id="5faf2-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="5faf2-107">Member name</span></span>|<span data-ttu-id="5faf2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5faf2-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="5faf2-109">Mantiene la compatibilidad con versiones anteriores de .NET Framework al hacer que las actualizaciones en memoria de los metadatos sean visibles.</span><span class="sxs-lookup"><span data-stu-id="5faf2-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="5faf2-110">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5faf2-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="5faf2-111">Hace que las actualizaciones en memoria de los metadatos sean visibles para el depurador.</span><span class="sxs-lookup"><span data-stu-id="5faf2-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5faf2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5faf2-112">Remarks</span></span>  
 <span data-ttu-id="5faf2-113">Un miembro de la `WriteableMetadataUpdateMode` enumeración puede pasarse a la [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) método para controlar si se actualiza en memoria a los metadatos en el proceso de destino son visibles para el depurador.</span><span class="sxs-lookup"><span data-stu-id="5faf2-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="5faf2-114">La opción `LegacyCompatPolicy` aplica el mismo comportamiento que en las versiones de .NET Framework anteriores a la 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="5faf2-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="5faf2-115">Esto suele significar que los metadatos de las actualizaciones no son visibles.</span><span class="sxs-lookup"><span data-stu-id="5faf2-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="5faf2-116">Sin embargo, las llamadas a varios métodos de depuración obligan implícitamente al depurador a hacer las actualizaciones visibles.</span><span class="sxs-lookup"><span data-stu-id="5faf2-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="5faf2-117">Por ejemplo, si el depurador pasa [ICorDebugILFrame:: GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) el índice de una variable no se encuentra en los metadatos del método original, todos los metadatos para el módulo se actualiza a una instantánea que coincida con el estado actual de la proceso.</span><span class="sxs-lookup"><span data-stu-id="5faf2-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="5faf2-118">En otras palabras, con la opción `LegacyCompatPolicy`, el depurador podría ver ninguna, algunas o todas las actualizaciones de metadatos disponibles, según cómo use otras partes de la API de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="5faf2-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5faf2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5faf2-119">Requirements</span></span>  
 <span data-ttu-id="5faf2-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5faf2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5faf2-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5faf2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5faf2-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5faf2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5faf2-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5faf2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5faf2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5faf2-124">See Also</span></span>  
 [<span data-ttu-id="5faf2-125">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="5faf2-125">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="5faf2-126">SetWriteableMetadataUpdateMode (método)</span><span class="sxs-lookup"><span data-stu-id="5faf2-126">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
