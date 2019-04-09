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
ms.openlocfilehash: 7024140ed9b870b5db38dba7e9b13321dd37386a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157591"
---
# <a name="cornativelink-structure"></a><span data-ttu-id="12112-102">COR_NATIVE_LINK (Estructura)</span><span class="sxs-lookup"><span data-stu-id="12112-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="12112-103">Contiene información que se utiliza para vincular el código nativo.</span><span class="sxs-lookup"><span data-stu-id="12112-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12112-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12112-104">Syntax</span></span>  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="12112-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="12112-105">Members</span></span>  
  
|<span data-ttu-id="12112-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="12112-106">Member</span></span>|<span data-ttu-id="12112-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="12112-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="12112-108">Tipo al que se vinculan en código nativo.</span><span class="sxs-lookup"><span data-stu-id="12112-108">The type to be linked in native code.</span></span> <span data-ttu-id="12112-109">Este valor es uno de los [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="12112-109">This value is one of the [CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="12112-110">Marcas usadas por el vinculador al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="12112-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="12112-111">Este valor es uno de los [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="12112-111">This value is one of the [CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="12112-112">El token de metadatos de MemberRef que representa el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="12112-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="12112-113">El formato es `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="12112-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12112-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12112-114">Requirements</span></span>  
 <span data-ttu-id="12112-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12112-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12112-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="12112-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12112-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12112-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="12112-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="12112-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12112-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="12112-119">See also</span></span>

- [<span data-ttu-id="12112-120">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="12112-120">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="12112-121">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="12112-121">CorNativeLinkType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)
- [<span data-ttu-id="12112-122">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="12112-122">CorNativeLinkFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
