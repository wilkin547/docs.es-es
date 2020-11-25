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
ms.openlocfilehash: d5f61aa9b4a65a5f33e64aa4441370c3f7ca5b03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732729"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="96ed9-102">CeeSectionRelocExtra (Unión)</span><span class="sxs-lookup"><span data-stu-id="96ed9-102">CeeSectionRelocExtra Union</span></span>

<span data-ttu-id="96ed9-103">Representa un desplazamiento de dirección que se usa en la interfaz [ICeeGen](iceegen-interface.md) para reubicar una sección.</span><span class="sxs-lookup"><span data-stu-id="96ed9-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96ed9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96ed9-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="96ed9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="96ed9-105">Members</span></span>  
  
|<span data-ttu-id="96ed9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="96ed9-106">Member</span></span>|<span data-ttu-id="96ed9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="96ed9-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="96ed9-108">Ajuste de la dirección superior para la sección.</span><span class="sxs-lookup"><span data-stu-id="96ed9-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96ed9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96ed9-109">Requirements</span></span>  

 <span data-ttu-id="96ed9-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96ed9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96ed9-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="96ed9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96ed9-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96ed9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96ed9-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96ed9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ed9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96ed9-114">See also</span></span>

- [<span data-ttu-id="96ed9-115">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="96ed9-115">Metadata Unions</span></span>](metadata-unions.md)
