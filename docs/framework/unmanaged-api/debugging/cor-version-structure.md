---
description: 'Más información acerca de: estructura de COR_VERSION'
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
ms.openlocfilehash: abdbe2a62d89db9dd673a429d81209fc42c34b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801779"
---
# <a name="cor_version-structure"></a><span data-ttu-id="dde03-103">COR_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="dde03-103">COR_VERSION Structure</span></span>

<span data-ttu-id="dde03-104">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="dde03-104">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde03-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dde03-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="dde03-106">Members</span><span class="sxs-lookup"><span data-stu-id="dde03-106">Members</span></span>  
  
|<span data-ttu-id="dde03-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="dde03-107">Member</span></span>|<span data-ttu-id="dde03-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dde03-108">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="dde03-109">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="dde03-109">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="dde03-110">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="dde03-110">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="dde03-111">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="dde03-111">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="dde03-112">Número de la subcompilación.</span><span class="sxs-lookup"><span data-stu-id="dde03-112">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde03-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dde03-113">Remarks</span></span>  

 <span data-ttu-id="dde03-114">Si el número de versión es 1.0.3705.288, 1 es el número de versión principal, 0 es el número de versión secundaria, 3705 es el número de compilación y 288 es el número de la subcompilación.</span><span class="sxs-lookup"><span data-stu-id="dde03-114">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde03-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dde03-115">Requirements</span></span>  

 <span data-ttu-id="dde03-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde03-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde03-117">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="dde03-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="dde03-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dde03-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dde03-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde03-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde03-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="dde03-120">See also</span></span>

- [<span data-ttu-id="dde03-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="dde03-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="dde03-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="dde03-122">Debugging</span></span>](index.md)
