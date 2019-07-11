---
title: COR_VERSION (Estructura)
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1f0a36d186c6d9788d43b075bf9d67c36ed1acb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740567"
---
# <a name="corversion-structure"></a><span data-ttu-id="9b92f-102">COR_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="9b92f-102">COR_VERSION Structure</span></span>
<span data-ttu-id="9b92f-103">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9b92f-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b92f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b92f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="9b92f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9b92f-105">Members</span></span>  
  
|<span data-ttu-id="9b92f-106">Member</span><span class="sxs-lookup"><span data-stu-id="9b92f-106">Member</span></span>|<span data-ttu-id="9b92f-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9b92f-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="9b92f-108">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="9b92f-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="9b92f-109">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="9b92f-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="9b92f-110">El número de compilación.</span><span class="sxs-lookup"><span data-stu-id="9b92f-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="9b92f-111">El número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="9b92f-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b92f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b92f-112">Remarks</span></span>  
 <span data-ttu-id="9b92f-113">Si el número de versión es 1.0.3705.288, 1 es el número de versión principal, 0 es el número de versión secundaria, 3705 es el número de compilación y 288 es el número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="9b92f-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b92f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b92f-114">Requirements</span></span>  
 <span data-ttu-id="9b92f-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b92f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b92f-116">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="9b92f-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="9b92f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b92f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b92f-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b92f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b92f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b92f-119">See also</span></span>

- [<span data-ttu-id="9b92f-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="9b92f-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="9b92f-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="9b92f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
