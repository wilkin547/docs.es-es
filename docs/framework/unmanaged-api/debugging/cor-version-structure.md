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
ms.openlocfilehash: ffbe571ebc3d14c12e57b1f805d77e56e97d12e1
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274172"
---
# <a name="cor_version-structure"></a><span data-ttu-id="27500-102">COR_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="27500-102">COR_VERSION Structure</span></span>
<span data-ttu-id="27500-103">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="27500-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27500-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27500-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="27500-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="27500-105">Members</span></span>  
  
|<span data-ttu-id="27500-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="27500-106">Member</span></span>|<span data-ttu-id="27500-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="27500-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="27500-108">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="27500-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="27500-109">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="27500-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="27500-110">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="27500-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="27500-111">Número de la subcompilación.</span><span class="sxs-lookup"><span data-stu-id="27500-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27500-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27500-112">Remarks</span></span>  
 <span data-ttu-id="27500-113">Si el número de versión es 1.0.3705.288, 1 es el número de versión principal, 0 es el número de versión secundaria, 3705 es el número de compilación y 288 es el número de la subcompilación.</span><span class="sxs-lookup"><span data-stu-id="27500-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27500-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27500-114">Requirements</span></span>  
 <span data-ttu-id="27500-115">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27500-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27500-116">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="27500-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="27500-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27500-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27500-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27500-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27500-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="27500-119">See also</span></span>

- [<span data-ttu-id="27500-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="27500-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="27500-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="27500-121">Debugging</span></span>](index.md)
