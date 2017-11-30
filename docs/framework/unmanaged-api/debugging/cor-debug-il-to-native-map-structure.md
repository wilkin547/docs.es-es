---
title: COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_DEBUG_IL_TO_NATIVE_MAP
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords: COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa191a4235defc5f47d0f7b3d823605da17fb5f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="99191-102">COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="99191-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="99191-103">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="99191-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99191-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99191-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="99191-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="99191-105">Members</span></span>  
  
|<span data-ttu-id="99191-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="99191-106">Member</span></span>|<span data-ttu-id="99191-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="99191-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="99191-108">El desplazamiento del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="99191-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="99191-109">El desplazamiento del inicio del código nativo.</span><span class="sxs-lookup"><span data-stu-id="99191-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="99191-110">El desplazamiento del final del código nativo.</span><span class="sxs-lookup"><span data-stu-id="99191-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99191-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99191-111">Requirements</span></span>  
 <span data-ttu-id="99191-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99191-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99191-113">**Encabezado:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="99191-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="99191-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99191-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99191-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99191-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99191-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="99191-116">See Also</span></span>  
 [<span data-ttu-id="99191-117">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="99191-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="99191-118">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="99191-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="99191-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="99191-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="99191-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="99191-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
