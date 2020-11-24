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
ms.openlocfilehash: 874c0520482cc5a3bbfcdd17924edee84fe91ff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675326"
---
# <a name="cor_version-structure"></a><span data-ttu-id="0226a-102">COR_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0226a-102">COR_VERSION Structure</span></span>

<span data-ttu-id="0226a-103">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0226a-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0226a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0226a-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="0226a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0226a-105">Members</span></span>  
  
|<span data-ttu-id="0226a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0226a-106">Member</span></span>|<span data-ttu-id="0226a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0226a-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="0226a-108">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="0226a-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="0226a-109">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="0226a-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="0226a-110">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="0226a-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="0226a-111">Número de la subcompilación.</span><span class="sxs-lookup"><span data-stu-id="0226a-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0226a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0226a-112">Remarks</span></span>  

 <span data-ttu-id="0226a-113">Si el número de versión es 1.0.3705.288, 1 es el número de versión principal, 0 es el número de versión secundaria, 3705 es el número de compilación y 288 es el número de la subcompilación.</span><span class="sxs-lookup"><span data-stu-id="0226a-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0226a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0226a-114">Requirements</span></span>  

 <span data-ttu-id="0226a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0226a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0226a-116">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="0226a-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0226a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0226a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0226a-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0226a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0226a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0226a-119">See also</span></span>

- [<span data-ttu-id="0226a-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="0226a-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0226a-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0226a-121">Debugging</span></span>](index.md)
