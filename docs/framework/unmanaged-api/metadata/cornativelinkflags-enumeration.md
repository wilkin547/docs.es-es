---
description: 'Más información sobre: enumeración CorNativeLinkFlags ('
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
ms.openlocfilehash: 9025d192ca92c1160c1b072b0dcfe045fa3ceab7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784358"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="ff69f-103">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ff69f-103">CorNativeLinkFlags Enumeration</span></span>

<span data-ttu-id="ff69f-104">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="ff69f-104">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff69f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff69f-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ff69f-106">Members</span><span class="sxs-lookup"><span data-stu-id="ff69f-106">Members</span></span>  
  
|<span data-ttu-id="ff69f-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="ff69f-107">Member</span></span>|<span data-ttu-id="ff69f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff69f-108">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="ff69f-109">Indica que no hay marcas.</span><span class="sxs-lookup"><span data-stu-id="ff69f-109">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="ff69f-110">Indica una `setLastError` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ff69f-110">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="ff69f-111">Indica una `nomangle` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ff69f-111">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="ff69f-112">No se usa.</span><span class="sxs-lookup"><span data-stu-id="ff69f-112">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff69f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff69f-113">Requirements</span></span>  

 <span data-ttu-id="ff69f-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff69f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff69f-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ff69f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff69f-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff69f-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff69f-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff69f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff69f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff69f-118">See also</span></span>

- [<span data-ttu-id="ff69f-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ff69f-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
