---
title: CodeChunkInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9d5ed028045f14012567ecfa86ff6a5c3d419a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977921"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="e7a3f-102">CodeChunkInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e7a3f-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="e7a3f-103">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="e7a3f-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7a3f-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="e7a3f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e7a3f-105">Members</span></span>  
  
|<span data-ttu-id="e7a3f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e7a3f-106">Member</span></span>|<span data-ttu-id="e7a3f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7a3f-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="e7a3f-108">Un `CORDB_ADDRESS` valor que especifica la dirección inicial del fragmento.</span><span class="sxs-lookup"><span data-stu-id="e7a3f-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="e7a3f-109">El tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="e7a3f-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7a3f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7a3f-110">Remarks</span></span>  
 <span data-ttu-id="e7a3f-111">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="e7a3f-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a3f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7a3f-112">Requirements</span></span>  
 <span data-ttu-id="e7a3f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7a3f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a3f-114">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="e7a3f-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="e7a3f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7a3f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7a3f-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a3f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a3f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7a3f-117">See also</span></span>
- [<span data-ttu-id="e7a3f-118">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="e7a3f-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="e7a3f-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e7a3f-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="e7a3f-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="e7a3f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
