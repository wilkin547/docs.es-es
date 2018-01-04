---
title: "CeeSectionRelocExtra (Unión)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocExtra Union
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocExtra
helpviewer_keywords: CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9591967dc70d54bd020414077fcc57b8007db9d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="327c1-102">CeeSectionRelocExtra (Unión)</span><span class="sxs-lookup"><span data-stu-id="327c1-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="327c1-103">Representa un desplazamiento de dirección que usa el [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaz para reubicar una sección.</span><span class="sxs-lookup"><span data-stu-id="327c1-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="327c1-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="327c1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="327c1-105">Members</span></span>  
  
|<span data-ttu-id="327c1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="327c1-106">Member</span></span>|<span data-ttu-id="327c1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="327c1-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="327c1-108">El ajuste de la dirección superior para la sección.</span><span class="sxs-lookup"><span data-stu-id="327c1-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="327c1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="327c1-109">Requirements</span></span>  
 <span data-ttu-id="327c1-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="327c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="327c1-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="327c1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="327c1-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="327c1-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="327c1-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="327c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="327c1-114">See Also</span></span>  
 [<span data-ttu-id="327c1-115">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="327c1-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
