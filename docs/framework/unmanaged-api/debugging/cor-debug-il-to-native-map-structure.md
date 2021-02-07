---
description: 'Más información acerca de: estructura de COR_DEBUG_IL_TO_NATIVE_MAP'
title: COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
ms.openlocfilehash: ec722b86f95e75d4ac00e04e8a602c6b6da64de5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747197"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="568ff-103">COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="568ff-103">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="568ff-104">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="568ff-104">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="568ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="568ff-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="568ff-106">Members</span><span class="sxs-lookup"><span data-stu-id="568ff-106">Members</span></span>  
  
|<span data-ttu-id="568ff-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="568ff-107">Member</span></span>|<span data-ttu-id="568ff-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="568ff-108">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="568ff-109">Desplazamiento del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="568ff-109">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="568ff-110">Desplazamiento del inicio del código nativo.</span><span class="sxs-lookup"><span data-stu-id="568ff-110">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="568ff-111">Desplazamiento del final del código nativo.</span><span class="sxs-lookup"><span data-stu-id="568ff-111">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="568ff-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="568ff-112">Requirements</span></span>  

 <span data-ttu-id="568ff-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="568ff-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="568ff-114">**Encabezado:** Corprof. idl, Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="568ff-114">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="568ff-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="568ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="568ff-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="568ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="568ff-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="568ff-117">See also</span></span>

- [<span data-ttu-id="568ff-118">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="568ff-118">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="568ff-119">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="568ff-119">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="568ff-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="568ff-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="568ff-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="568ff-121">Debugging</span></span>](index.md)
