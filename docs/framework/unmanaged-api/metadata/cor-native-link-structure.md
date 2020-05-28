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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007980"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="ba62d-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ba62d-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="ba62d-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="ba62d-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba62d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba62d-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="ba62d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ba62d-105">Members</span></span>  
  
|<span data-ttu-id="ba62d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ba62d-106">Member</span></span>|<span data-ttu-id="ba62d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba62d-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="ba62d-108">Tipo que se va a vincular en código nativo.</span><span class="sxs-lookup"><span data-stu-id="ba62d-108">The type to be linked in native code.</span></span> <span data-ttu-id="ba62d-109">Este valor es uno de los valores de [cornativelinktype (](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ba62d-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="ba62d-110">Marcas usadas por el enlazador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="ba62d-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="ba62d-111">Este valor es uno de los valores de [CorNativeLinkFlags (](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ba62d-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="ba62d-112">Símbolo (token) de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="ba62d-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="ba62d-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="ba62d-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba62d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba62d-114">Requirements</span></span>  
 <span data-ttu-id="ba62d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba62d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba62d-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba62d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba62d-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba62d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba62d-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba62d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba62d-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba62d-119">See also</span></span>

- [<span data-ttu-id="ba62d-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="ba62d-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="ba62d-121">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ba62d-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="ba62d-122">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ba62d-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
