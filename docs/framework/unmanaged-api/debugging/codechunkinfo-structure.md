---
description: 'Más información acerca de: estructura CodeChunkInfo ('
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
ms.openlocfilehash: 017a9ee8c608d4efae98eb0a342a3371ef8ec310
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712355"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="35375-103">Estructura CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="35375-103">CodeChunkInfo Structure</span></span>

<span data-ttu-id="35375-104">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="35375-104">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35375-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35375-105">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="35375-106">Members</span><span class="sxs-lookup"><span data-stu-id="35375-106">Members</span></span>  
  
|<span data-ttu-id="35375-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="35375-107">Member</span></span>|<span data-ttu-id="35375-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="35375-108">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="35375-109">`CORDB_ADDRESS`Valor que especifica la dirección de inicio del fragmento.</span><span class="sxs-lookup"><span data-stu-id="35375-109">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="35375-110">Tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="35375-110">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35375-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35375-111">Remarks</span></span>  

 <span data-ttu-id="35375-112">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="35375-112">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35375-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35375-113">Requirements</span></span>  

 <span data-ttu-id="35375-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35375-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35375-115">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="35375-115">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="35375-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35375-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35375-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35375-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35375-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="35375-118">See also</span></span>

- [<span data-ttu-id="35375-119">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="35375-119">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="35375-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="35375-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="35375-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="35375-121">Debugging</span></span>](index.md)
