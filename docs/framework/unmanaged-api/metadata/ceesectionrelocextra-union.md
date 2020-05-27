---
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
ms.openlocfilehash: d11fefe220fdb00457cc48a6cd166673350be049
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006043"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="5c6d4-102">CeeSectionRelocExtra (Unión)</span><span class="sxs-lookup"><span data-stu-id="5c6d4-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="5c6d4-103">Representa un desplazamiento de dirección que se usa en la interfaz [ICeeGen](iceegen-interface.md) para reubicar una sección.</span><span class="sxs-lookup"><span data-stu-id="5c6d4-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c6d4-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="5c6d4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5c6d4-105">Members</span></span>  
  
|<span data-ttu-id="5c6d4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5c6d4-106">Member</span></span>|<span data-ttu-id="5c6d4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c6d4-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="5c6d4-108">Ajuste de la dirección superior para la sección.</span><span class="sxs-lookup"><span data-stu-id="5c6d4-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c6d4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c6d4-109">Requirements</span></span>  
 <span data-ttu-id="5c6d4-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6d4-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c6d4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c6d4-112">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c6d4-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c6d4-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6d4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6d4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c6d4-114">See also</span></span>

- [<span data-ttu-id="5c6d4-115">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="5c6d4-115">Metadata Unions</span></span>](metadata-unions.md)
