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
ms.openlocfilehash: ef9b177bee0651b6b8ea994610315ce93524e8e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676938"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="d3fff-102">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d3fff-102">CorNativeLinkFlags Enumeration</span></span>

<span data-ttu-id="d3fff-103">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="d3fff-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3fff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3fff-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d3fff-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d3fff-105">Members</span></span>  
  
|<span data-ttu-id="d3fff-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d3fff-106">Member</span></span>|<span data-ttu-id="d3fff-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3fff-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="d3fff-108">Indica que no hay marcas.</span><span class="sxs-lookup"><span data-stu-id="d3fff-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="d3fff-109">Indica una `setLastError` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d3fff-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="d3fff-110">Indica una `nomangle` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d3fff-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="d3fff-111">No se usa.</span><span class="sxs-lookup"><span data-stu-id="d3fff-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3fff-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3fff-112">Requirements</span></span>  

 <span data-ttu-id="d3fff-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3fff-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3fff-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d3fff-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3fff-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3fff-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3fff-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3fff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3fff-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3fff-117">See also</span></span>

- [<span data-ttu-id="d3fff-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="d3fff-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
