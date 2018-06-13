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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c7634ec801a30aa7ba07954c1df0c3d37ec279eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440306"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="60b77-102">CeeSectionRelocExtra (Unión)</span><span class="sxs-lookup"><span data-stu-id="60b77-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="60b77-103">Representa un desplazamiento de dirección que usa el [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaz para reubicar una sección.</span><span class="sxs-lookup"><span data-stu-id="60b77-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60b77-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="60b77-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="60b77-105">Members</span></span>  
  
|<span data-ttu-id="60b77-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="60b77-106">Member</span></span>|<span data-ttu-id="60b77-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="60b77-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="60b77-108">El ajuste de la dirección superior para la sección.</span><span class="sxs-lookup"><span data-stu-id="60b77-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60b77-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60b77-109">Requirements</span></span>  
 <span data-ttu-id="60b77-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60b77-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60b77-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="60b77-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60b77-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60b77-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60b77-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60b77-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b77-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60b77-114">See Also</span></span>  
 [<span data-ttu-id="60b77-115">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="60b77-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
