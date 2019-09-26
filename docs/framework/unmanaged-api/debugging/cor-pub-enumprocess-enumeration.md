---
title: COR_PUB_ENUMPROCESS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eab5fc13b74d8af4f0baaa3953c5c73ea255bfe6
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274022"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="f0500-102">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f0500-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="f0500-103">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="f0500-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0500-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0500-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="f0500-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f0500-105">Members</span></span>  
  
|<span data-ttu-id="f0500-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="f0500-106">Member name</span></span>|<span data-ttu-id="f0500-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0500-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="f0500-108">Un proceso administrado.</span><span class="sxs-lookup"><span data-stu-id="f0500-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0500-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0500-109">Remarks</span></span>  
 <span data-ttu-id="f0500-110">La versión actual de la API de depuración no administrada solo enumera los procesos administrados.</span><span class="sxs-lookup"><span data-stu-id="f0500-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0500-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0500-111">Requirements</span></span>  
 <span data-ttu-id="f0500-112">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0500-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0500-113">**Encabezado**: CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f0500-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f0500-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0500-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0500-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0500-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0500-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0500-116">See also</span></span>

- [<span data-ttu-id="f0500-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="f0500-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
