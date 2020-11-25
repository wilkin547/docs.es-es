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
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724174"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="6fb13-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="6fb13-102">COR_NATIVE_LINK Structure</span></span>

<span data-ttu-id="6fb13-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="6fb13-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fb13-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="6fb13-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6fb13-105">Members</span></span>  
  
|<span data-ttu-id="6fb13-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6fb13-106">Member</span></span>|<span data-ttu-id="6fb13-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fb13-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="6fb13-108">Tipo que se va a vincular en código nativo.</span><span class="sxs-lookup"><span data-stu-id="6fb13-108">The type to be linked in native code.</span></span> <span data-ttu-id="6fb13-109">Este valor es uno de los valores de [cornativelinktype (](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6fb13-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="6fb13-110">Marcas usadas por el enlazador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="6fb13-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="6fb13-111">Este valor es uno de los valores de [CorNativeLinkFlags (](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6fb13-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="6fb13-112">Símbolo (token) de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6fb13-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="6fb13-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="6fb13-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fb13-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fb13-114">Requirements</span></span>  

 <span data-ttu-id="6fb13-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fb13-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fb13-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6fb13-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fb13-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6fb13-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fb13-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb13-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb13-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fb13-119">See also</span></span>

- [<span data-ttu-id="6fb13-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="6fb13-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="6fb13-121">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6fb13-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="6fb13-122">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6fb13-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
