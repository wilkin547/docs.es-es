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
ms.openlocfilehash: d03c22c455f0e44ce32d4593d9eee50ceef94a22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443945"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="8acbe-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8acbe-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="8acbe-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="8acbe-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8acbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8acbe-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="8acbe-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8acbe-105">Members</span></span>  
  
|<span data-ttu-id="8acbe-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8acbe-106">Member</span></span>|<span data-ttu-id="8acbe-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8acbe-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="8acbe-108">The type to be linked in native code.</span><span class="sxs-lookup"><span data-stu-id="8acbe-108">The type to be linked in native code.</span></span> <span data-ttu-id="8acbe-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="8acbe-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="8acbe-110">Flags used by the linker when linking native code.</span><span class="sxs-lookup"><span data-stu-id="8acbe-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="8acbe-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="8acbe-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="8acbe-112">The MemberRef metadata token that represents the entry point.</span><span class="sxs-lookup"><span data-stu-id="8acbe-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="8acbe-113">The format is `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="8acbe-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8acbe-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8acbe-114">Requirements</span></span>  
 <span data-ttu-id="8acbe-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8acbe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8acbe-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8acbe-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8acbe-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8acbe-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8acbe-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8acbe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acbe-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8acbe-119">See also</span></span>

- [<span data-ttu-id="8acbe-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="8acbe-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="8acbe-121">CorNativeLinkType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="8acbe-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="8acbe-122">CorNativeLinkFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="8acbe-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
