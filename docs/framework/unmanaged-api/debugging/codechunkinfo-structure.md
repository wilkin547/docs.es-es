---
title: CodeChunkInfo estructura-1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CodeChunkInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: CodeChunkInfo
helpviewer_keywords: CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17727c8927f9db3de3ab26d2504dfae5215a1495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="7aad3-102">CodeChunkInfo estructura-1</span><span class="sxs-lookup"><span data-stu-id="7aad3-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="7aad3-103">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="7aad3-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aad3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7aad3-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="7aad3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7aad3-105">Members</span></span>  
  
|<span data-ttu-id="7aad3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7aad3-106">Member</span></span>|<span data-ttu-id="7aad3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7aad3-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="7aad3-108">Un `CORDB_ADDRESS` valor que especifica la dirección inicial del fragmento.</span><span class="sxs-lookup"><span data-stu-id="7aad3-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="7aad3-109">El tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="7aad3-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aad3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7aad3-110">Remarks</span></span>  
 <span data-ttu-id="7aad3-111">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="7aad3-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aad3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7aad3-112">Requirements</span></span>  
 <span data-ttu-id="7aad3-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aad3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aad3-114">**Encabezado:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="7aad3-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="7aad3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7aad3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7aad3-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aad3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aad3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aad3-117">See Also</span></span>  
 [<span data-ttu-id="7aad3-118">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="7aad3-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="7aad3-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="7aad3-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="7aad3-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="7aad3-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
