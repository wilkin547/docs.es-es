---
title: COR_NATIVE_LINK (Estructura)
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08d27eb834c1a9a3a5d163bb2d3054f599ae1669
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719565"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="bb10b-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="bb10b-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="bb10b-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="bb10b-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb10b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb10b-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="bb10b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bb10b-105">Members</span></span>  
  
|<span data-ttu-id="bb10b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="bb10b-106">Member</span></span>|<span data-ttu-id="bb10b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb10b-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="bb10b-108">Tipo al que se vinculan en código nativo.</span><span class="sxs-lookup"><span data-stu-id="bb10b-108">The type to be linked in native code.</span></span> <span data-ttu-id="bb10b-109">Este valor es uno de los [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="bb10b-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="bb10b-110">Marcas usadas por el vinculador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="bb10b-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="bb10b-111">Este valor es uno de los [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="bb10b-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="bb10b-112">El token de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="bb10b-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="bb10b-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="bb10b-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb10b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb10b-114">Requirements</span></span>  
 <span data-ttu-id="bb10b-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb10b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb10b-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb10b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb10b-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb10b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb10b-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb10b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb10b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb10b-119">See also</span></span>
- [<span data-ttu-id="bb10b-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="bb10b-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="bb10b-121">CorNativeLinkType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="bb10b-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="bb10b-122">CorNativeLinkFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="bb10b-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
