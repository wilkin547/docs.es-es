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
ms.openlocfilehash: 812b70a594b5aa933f52d36f32d96d712267ecf4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177954"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="d0fcd-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d0fcd-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="d0fcd-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0fcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0fcd-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="d0fcd-105">Members</span><span class="sxs-lookup"><span data-stu-id="d0fcd-105">Members</span></span>  
  
|<span data-ttu-id="d0fcd-106">Member</span><span class="sxs-lookup"><span data-stu-id="d0fcd-106">Member</span></span>|<span data-ttu-id="d0fcd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0fcd-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="d0fcd-108">El tipo que se va a vincular en código nativo.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-108">The type to be linked in native code.</span></span> <span data-ttu-id="d0fcd-109">Este valor es uno de los [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="d0fcd-110">Indicadores utilizados por el vinculador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="d0fcd-111">Este valor es uno de los [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="d0fcd-112">El token de metadatos MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="d0fcd-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="d0fcd-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0fcd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0fcd-114">Requirements</span></span>  
 <span data-ttu-id="d0fcd-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0fcd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0fcd-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0fcd-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0fcd-117">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0fcd-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0fcd-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0fcd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fcd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0fcd-119">See also</span></span>

- [<span data-ttu-id="d0fcd-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="d0fcd-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="d0fcd-121">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d0fcd-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="d0fcd-122">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d0fcd-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
