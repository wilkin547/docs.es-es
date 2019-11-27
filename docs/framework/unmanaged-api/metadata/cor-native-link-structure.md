---
title: COR_NATIVE_LINK (estructura)
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
# <a name="cor_native_link-structure"></a><span data-ttu-id="77db1-102">COR_NATIVE_LINK (estructura)</span><span class="sxs-lookup"><span data-stu-id="77db1-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="77db1-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="77db1-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77db1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77db1-104">Syntax</span></span>  
  
```cpp  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="77db1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="77db1-105">Members</span></span>  
  
|<span data-ttu-id="77db1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="77db1-106">Member</span></span>|<span data-ttu-id="77db1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="77db1-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="77db1-108">Tipo que se va a vincular en código nativo.</span><span class="sxs-lookup"><span data-stu-id="77db1-108">The type to be linked in native code.</span></span> <span data-ttu-id="77db1-109">Este valor es uno de los valores de [cornativelinktype (](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="77db1-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="77db1-110">Marcas usadas por el enlazador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="77db1-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="77db1-111">Este valor es uno de los valores de [CorNativeLinkFlags (](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="77db1-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="77db1-112">Símbolo (token) de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="77db1-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="77db1-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="77db1-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77db1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77db1-114">Requirements</span></span>  
 <span data-ttu-id="77db1-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77db1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77db1-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="77db1-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77db1-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="77db1-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77db1-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77db1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77db1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="77db1-119">See also</span></span>

- [<span data-ttu-id="77db1-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="77db1-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="77db1-121">CorNativeLinkType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="77db1-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="77db1-122">CorNativeLinkFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="77db1-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
