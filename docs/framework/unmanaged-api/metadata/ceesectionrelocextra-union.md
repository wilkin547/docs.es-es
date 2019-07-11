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
ms.openlocfilehash: c2e73caa3c69090bca30c8d4a907ddb619bd0ed4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776323"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="da194-102">CeeSectionRelocExtra (Unión)</span><span class="sxs-lookup"><span data-stu-id="da194-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="da194-103">Representa un desplazamiento de dirección que usa el [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaz para reubicar una sección.</span><span class="sxs-lookup"><span data-stu-id="da194-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da194-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da194-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="da194-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="da194-105">Members</span></span>  
  
|<span data-ttu-id="da194-106">Member</span><span class="sxs-lookup"><span data-stu-id="da194-106">Member</span></span>|<span data-ttu-id="da194-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da194-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="da194-108">El ajuste de la dirección superior de la sección.</span><span class="sxs-lookup"><span data-stu-id="da194-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da194-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da194-109">Requirements</span></span>  
 <span data-ttu-id="da194-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da194-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da194-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="da194-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da194-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da194-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da194-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da194-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da194-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="da194-114">See also</span></span>

- [<span data-ttu-id="da194-115">Uniones de metadatos</span><span class="sxs-lookup"><span data-stu-id="da194-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
