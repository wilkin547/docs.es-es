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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: babb1ace1385c241b782691f22bfb4fbb689e310
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274078"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="88fcb-102">COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="88fcb-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="88fcb-103">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="88fcb-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88fcb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88fcb-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="88fcb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="88fcb-105">Members</span></span>  
  
|<span data-ttu-id="88fcb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="88fcb-106">Member</span></span>|<span data-ttu-id="88fcb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="88fcb-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="88fcb-108">Desplazamiento del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="88fcb-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="88fcb-109">Desplazamiento del inicio del código nativo.</span><span class="sxs-lookup"><span data-stu-id="88fcb-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="88fcb-110">Desplazamiento del final del código nativo.</span><span class="sxs-lookup"><span data-stu-id="88fcb-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88fcb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88fcb-111">Requirements</span></span>  
 <span data-ttu-id="88fcb-112">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88fcb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88fcb-113">**Encabezado**: Corprof. idl, Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="88fcb-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="88fcb-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88fcb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88fcb-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88fcb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fcb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="88fcb-116">See also</span></span>

- [<span data-ttu-id="88fcb-117">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="88fcb-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="88fcb-118">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="88fcb-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="88fcb-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="88fcb-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="88fcb-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="88fcb-120">Debugging</span></span>](index.md)
