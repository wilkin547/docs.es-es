---
title: COR_NATIVE_LINK (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_NATIVE_LINK
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_NATIVE_LINK
helpviewer_keywords: COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e27b66fce8a78ef0feb7ed10e77cc51fc1fe83c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cornativelink-structure"></a><span data-ttu-id="b668a-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b668a-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="b668a-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="b668a-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b668a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b668a-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="b668a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b668a-105">Members</span></span>  
  
|<span data-ttu-id="b668a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b668a-106">Member</span></span>|<span data-ttu-id="b668a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b668a-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="b668a-108">El tipo esté vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="b668a-108">The type to be linked in native code.</span></span> <span data-ttu-id="b668a-109">Este valor es uno de los [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="b668a-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="b668a-110">Marcadores utilizados por el vinculador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="b668a-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="b668a-111">Este valor es uno de los [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="b668a-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="b668a-112">El token de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="b668a-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="b668a-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="b668a-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b668a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b668a-114">Requirements</span></span>  
 <span data-ttu-id="b668a-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b668a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b668a-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b668a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b668a-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b668a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b668a-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b668a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b668a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b668a-119">See Also</span></span>  
 [<span data-ttu-id="b668a-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="b668a-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="b668a-121">CorNativeLinkType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b668a-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [<span data-ttu-id="b668a-122">CorNativeLinkFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b668a-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
