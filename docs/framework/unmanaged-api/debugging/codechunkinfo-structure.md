---
title: Estructura CodeChunkInfo
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
ms.openlocfilehash: 58c9d4c66af0bb9f4e66d17b18ac78ef8271bc31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609612"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="b5860-102">Estructura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="b5860-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="b5860-103">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b5860-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5860-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5860-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="b5860-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b5860-105">Members</span></span>  
  
|<span data-ttu-id="b5860-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b5860-106">Member</span></span>|<span data-ttu-id="b5860-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5860-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="b5860-108">Un `CORDB_ADDRESS` valor que especifica la dirección inicial del fragmento.</span><span class="sxs-lookup"><span data-stu-id="b5860-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="b5860-109">El tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="b5860-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5860-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5860-110">Remarks</span></span>  
 <span data-ttu-id="b5860-111">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="b5860-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5860-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5860-112">Requirements</span></span>  
 <span data-ttu-id="b5860-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5860-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5860-114">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b5860-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b5860-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5860-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5860-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5860-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5860-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5860-117">See also</span></span>

- [<span data-ttu-id="b5860-118">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="b5860-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="b5860-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b5860-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="b5860-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="b5860-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
