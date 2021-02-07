---
description: 'Más información acerca de: estructura de COR_NATIVE_LINK'
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
ms.openlocfilehash: 09c715af698a0614fd4a9a17679df6908a1497a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678580"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="d172c-103">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d172c-103">COR_NATIVE_LINK Structure</span></span>

<span data-ttu-id="d172c-104">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="d172c-104">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d172c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d172c-105">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="d172c-106">Members</span><span class="sxs-lookup"><span data-stu-id="d172c-106">Members</span></span>  
  
|<span data-ttu-id="d172c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="d172c-107">Member</span></span>|<span data-ttu-id="d172c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d172c-108">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="d172c-109">Tipo que se va a vincular en código nativo.</span><span class="sxs-lookup"><span data-stu-id="d172c-109">The type to be linked in native code.</span></span> <span data-ttu-id="d172c-110">Este valor es uno de los valores de [cornativelinktype (](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d172c-110">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="d172c-111">Marcas usadas por el enlazador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="d172c-111">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="d172c-112">Este valor es uno de los valores de [CorNativeLinkFlags (](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d172c-112">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="d172c-113">Símbolo (token) de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="d172c-113">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="d172c-114">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="d172c-114">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d172c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d172c-115">Requirements</span></span>  

 <span data-ttu-id="d172c-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d172c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d172c-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d172c-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d172c-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d172c-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d172c-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d172c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d172c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d172c-120">See also</span></span>

- [<span data-ttu-id="d172c-121">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="d172c-121">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="d172c-122">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d172c-122">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="d172c-123">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d172c-123">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
