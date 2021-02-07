---
description: 'Más información sobre: Ceesectionrelocextra (Union'
title: CeeSectionRelocExtra (Unión)
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: 40001c1a0772e24633f4232da8e7817f3747f8ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678853"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="b6760-103">CeeSectionRelocExtra (Unión)</span><span class="sxs-lookup"><span data-stu-id="b6760-103">CeeSectionRelocExtra Union</span></span>

<span data-ttu-id="b6760-104">Representa un desplazamiento de dirección que se usa en la interfaz [ICeeGen](iceegen-interface.md) para reubicar una sección.</span><span class="sxs-lookup"><span data-stu-id="b6760-104">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6760-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6760-105">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="b6760-106">Members</span><span class="sxs-lookup"><span data-stu-id="b6760-106">Members</span></span>  
  
|<span data-ttu-id="b6760-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b6760-107">Member</span></span>|<span data-ttu-id="b6760-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6760-108">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="b6760-109">Ajuste de la dirección superior para la sección.</span><span class="sxs-lookup"><span data-stu-id="b6760-109">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6760-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6760-110">Requirements</span></span>  

 <span data-ttu-id="b6760-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6760-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6760-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6760-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6760-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6760-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6760-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6760-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6760-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6760-115">See also</span></span>

- [<span data-ttu-id="b6760-116">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="b6760-116">Metadata Unions</span></span>](metadata-unions.md)
