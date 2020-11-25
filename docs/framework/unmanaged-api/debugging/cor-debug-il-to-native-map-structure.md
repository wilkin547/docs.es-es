---
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
ms.openlocfilehash: 61544d0dfe876f35fdfbe5afa945fad0620c0eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726657"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="7b8b7-102">COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="7b8b7-103">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b8b7-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="7b8b7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7b8b7-105">Members</span></span>  
  
|<span data-ttu-id="7b8b7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7b8b7-106">Member</span></span>|<span data-ttu-id="7b8b7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b8b7-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="7b8b7-108">Desplazamiento del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="7b8b7-109">Desplazamiento del inicio del código nativo.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="7b8b7-110">Desplazamiento del final del código nativo.</span><span class="sxs-lookup"><span data-stu-id="7b8b7-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b8b7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b8b7-111">Requirements</span></span>  

 <span data-ttu-id="7b8b7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b8b7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b8b7-113">**Encabezado:** Corprof. idl, Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="7b8b7-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="7b8b7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b8b7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b8b7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b8b7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8b7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b8b7-116">See also</span></span>

- [<span data-ttu-id="7b8b7-117">GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="7b8b7-118">GetILToNativeMapping (Método)</span><span class="sxs-lookup"><span data-stu-id="7b8b7-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="7b8b7-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="7b8b7-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="7b8b7-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="7b8b7-120">Debugging</span></span>](index.md)
