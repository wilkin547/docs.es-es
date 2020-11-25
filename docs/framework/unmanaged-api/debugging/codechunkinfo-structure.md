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
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727437"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="af0ab-102">Estructura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="af0ab-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="af0ab-103">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="af0ab-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af0ab-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="af0ab-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="af0ab-105">Members</span></span>  
  
|<span data-ttu-id="af0ab-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="af0ab-106">Member</span></span>|<span data-ttu-id="af0ab-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="af0ab-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="af0ab-108">`CORDB_ADDRESS`Valor que especifica la dirección de inicio del fragmento.</span><span class="sxs-lookup"><span data-stu-id="af0ab-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="af0ab-109">Tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="af0ab-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af0ab-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af0ab-110">Remarks</span></span>  

 <span data-ttu-id="af0ab-111">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="af0ab-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0ab-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af0ab-112">Requirements</span></span>  

 <span data-ttu-id="af0ab-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af0ab-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af0ab-114">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="af0ab-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="af0ab-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af0ab-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af0ab-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af0ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0ab-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af0ab-117">See also</span></span>

- [<span data-ttu-id="af0ab-118">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="af0ab-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="af0ab-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="af0ab-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="af0ab-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="af0ab-120">Debugging</span></span>](index.md)
