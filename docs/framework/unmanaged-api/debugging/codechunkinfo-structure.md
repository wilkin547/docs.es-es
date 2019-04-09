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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072667"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="37f2d-102">Estructura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="37f2d-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="37f2d-103">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="37f2d-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37f2d-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="37f2d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="37f2d-105">Members</span></span>  
  
|<span data-ttu-id="37f2d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="37f2d-106">Member</span></span>|<span data-ttu-id="37f2d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f2d-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="37f2d-108">Un `CORDB_ADDRESS` valor que especifica la dirección inicial del fragmento.</span><span class="sxs-lookup"><span data-stu-id="37f2d-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="37f2d-109">El tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="37f2d-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37f2d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37f2d-110">Remarks</span></span>  
 <span data-ttu-id="37f2d-111">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="37f2d-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37f2d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37f2d-112">Requirements</span></span>  
 <span data-ttu-id="37f2d-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37f2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37f2d-114">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="37f2d-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="37f2d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37f2d-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="37f2d-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="37f2d-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37f2d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f2d-117">See also</span></span>

- [<span data-ttu-id="37f2d-118">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="37f2d-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="37f2d-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="37f2d-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="37f2d-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="37f2d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
