---
title: CorNativeLinkFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98a83a64a692955d5627e891e7fb3a3ef6f53476
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442574"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="76aa7-102">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="76aa7-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="76aa7-103">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="76aa7-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76aa7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76aa7-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="76aa7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="76aa7-105">Members</span></span>  
  
|<span data-ttu-id="76aa7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="76aa7-106">Member</span></span>|<span data-ttu-id="76aa7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76aa7-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="76aa7-108">Indica que no existen marcadores.</span><span class="sxs-lookup"><span data-stu-id="76aa7-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="76aa7-109">Indica un `setLastError` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="76aa7-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="76aa7-110">Indica un `nomangle` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="76aa7-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="76aa7-111">No usado.</span><span class="sxs-lookup"><span data-stu-id="76aa7-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76aa7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76aa7-112">Requirements</span></span>  
 <span data-ttu-id="76aa7-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76aa7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76aa7-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="76aa7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76aa7-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76aa7-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76aa7-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76aa7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76aa7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="76aa7-117">See Also</span></span>  
 [<span data-ttu-id="76aa7-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="76aa7-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
