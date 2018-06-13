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
ms.openlocfilehash: 2ea9a75ae9316c18439f6c2b728b47deacef9228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404746"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="ed0c1-102">COR_DEBUG_IL_TO_NATIVE_MAP (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ed0c1-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="ed0c1-103">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="ed0c1-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed0c1-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="ed0c1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ed0c1-105">Members</span></span>  
  
|<span data-ttu-id="ed0c1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ed0c1-106">Member</span></span>|<span data-ttu-id="ed0c1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed0c1-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="ed0c1-108">El desplazamiento del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="ed0c1-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="ed0c1-109">El desplazamiento del inicio del código nativo.</span><span class="sxs-lookup"><span data-stu-id="ed0c1-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="ed0c1-110">El desplazamiento del final del código nativo.</span><span class="sxs-lookup"><span data-stu-id="ed0c1-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed0c1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed0c1-111">Requirements</span></span>  
 <span data-ttu-id="ed0c1-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed0c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed0c1-113">**Encabezado:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="ed0c1-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="ed0c1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed0c1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed0c1-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed0c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0c1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed0c1-116">See Also</span></span>  
 [<span data-ttu-id="ed0c1-117">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="ed0c1-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="ed0c1-118">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="ed0c1-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="ed0c1-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="ed0c1-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="ed0c1-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="ed0c1-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
