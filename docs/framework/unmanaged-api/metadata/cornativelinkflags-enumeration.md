---
title: CorNativeLinkFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e6eb2a30dd6722309fd80c1611ad9200ab14ae5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045456"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="a381d-102">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a381d-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="a381d-103">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="a381d-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a381d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a381d-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a381d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a381d-105">Members</span></span>  
  
|<span data-ttu-id="a381d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a381d-106">Member</span></span>|<span data-ttu-id="a381d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a381d-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="a381d-108">Indica que no hay marcas.</span><span class="sxs-lookup"><span data-stu-id="a381d-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="a381d-109">Indica un `setLastError` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a381d-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="a381d-110">Indica un `nomangle` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a381d-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="a381d-111">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a381d-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a381d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a381d-112">Requirements</span></span>  
 <span data-ttu-id="a381d-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a381d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a381d-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a381d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a381d-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a381d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a381d-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a381d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a381d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a381d-117">See also</span></span>

- [<span data-ttu-id="a381d-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a381d-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
