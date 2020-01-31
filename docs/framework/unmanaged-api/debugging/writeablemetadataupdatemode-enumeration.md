---
title: WriteableMetadataUpdateMode (enumeración)
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
ms.openlocfilehash: 5c3f2f7a9c0804b71c9c8a52bb032aca7c03825e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790292"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="386ea-102">WriteableMetadataUpdateMode (enumeración)</span><span class="sxs-lookup"><span data-stu-id="386ea-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="386ea-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="386ea-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="386ea-104">Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.</span><span class="sxs-lookup"><span data-stu-id="386ea-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="386ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="386ea-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="386ea-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="386ea-106">Members</span></span>  
  
|<span data-ttu-id="386ea-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="386ea-107">Member name</span></span>|<span data-ttu-id="386ea-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="386ea-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="386ea-109">Mantiene la compatibilidad con versiones anteriores de .NET Framework al hacer que las actualizaciones en memoria de los metadatos sean visibles.</span><span class="sxs-lookup"><span data-stu-id="386ea-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="386ea-110">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="386ea-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="386ea-111">Hace que las actualizaciones en memoria de los metadatos sean visibles para el depurador.</span><span class="sxs-lookup"><span data-stu-id="386ea-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="386ea-112">Notas</span><span class="sxs-lookup"><span data-stu-id="386ea-112">Remarks</span></span>  
 <span data-ttu-id="386ea-113">Un miembro de la enumeración `WriteableMetadataUpdateMode` se puede pasar al método [setwriteablemetadataupdatemode (](icordebugprocess7-setwriteablemetadataupdatemode-method.md) para controlar si las actualizaciones en memoria de los metadatos en el proceso de destino son visibles para el depurador.</span><span class="sxs-lookup"><span data-stu-id="386ea-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="386ea-114">La opción `LegacyCompatPolicy` aplica el mismo comportamiento que en las versiones de .NET Framework anteriores a la 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="386ea-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="386ea-115">Esto suele significar que los metadatos de las actualizaciones no son visibles.</span><span class="sxs-lookup"><span data-stu-id="386ea-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="386ea-116">Sin embargo, las llamadas a varios métodos de depuración obligan implícitamente al depurador a hacer las actualizaciones visibles.</span><span class="sxs-lookup"><span data-stu-id="386ea-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="386ea-117">Por ejemplo, si el depurador pasa [ICorDebugILFrame:: getlocalvariable (](icordebugilframe-getlocalvariable-method.md) , el índice de una variable no se encuentra en los metadatos originales del método, todos los metadatos del módulo se actualizan a una instantánea que coincide con el estado actual del proceso.</span><span class="sxs-lookup"><span data-stu-id="386ea-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="386ea-118">En otras palabras, con la opción `LegacyCompatPolicy`, el depurador podría ver ninguna, algunas o todas las actualizaciones de metadatos disponibles, según cómo use otras partes de la API de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="386ea-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="386ea-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="386ea-119">Requirements</span></span>  
 <span data-ttu-id="386ea-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="386ea-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="386ea-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="386ea-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="386ea-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="386ea-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="386ea-123">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="386ea-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="386ea-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="386ea-124">See also</span></span>

- [<span data-ttu-id="386ea-125">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="386ea-125">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="386ea-126">SetWriteableMetadataUpdateMode (método)</span><span class="sxs-lookup"><span data-stu-id="386ea-126">SetWriteableMetadataUpdateMode Method</span></span>](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
