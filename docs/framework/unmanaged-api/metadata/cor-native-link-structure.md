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
ms.openlocfilehash: d0d9b8a9a1014d98c51f1471f8203be07f7ff49c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440962"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="99938-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="99938-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="99938-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="99938-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99938-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99938-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="99938-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="99938-105">Members</span></span>  
  
|<span data-ttu-id="99938-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="99938-106">Member</span></span>|<span data-ttu-id="99938-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="99938-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="99938-108">El tipo esté vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="99938-108">The type to be linked in native code.</span></span> <span data-ttu-id="99938-109">Este valor es uno de los [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="99938-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="99938-110">Marcadores utilizados por el vinculador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="99938-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="99938-111">Este valor es uno de los [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="99938-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="99938-112">El token de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="99938-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="99938-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="99938-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99938-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99938-114">Requirements</span></span>  
 <span data-ttu-id="99938-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99938-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99938-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99938-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99938-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99938-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99938-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99938-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99938-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="99938-119">See Also</span></span>  
 [<span data-ttu-id="99938-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="99938-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="99938-121">CorNativeLinkType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="99938-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="99938-122">CorNativeLinkFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="99938-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
