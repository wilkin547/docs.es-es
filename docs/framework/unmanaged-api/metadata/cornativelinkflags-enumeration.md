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
ms.openlocfilehash: 6be71878ba354ebe53b4b8b9b40db3222ec828f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781737"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="a1bb8-102">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a1bb8-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="a1bb8-103">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="a1bb8-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1bb8-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a1bb8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a1bb8-105">Members</span></span>  
  
|<span data-ttu-id="a1bb8-106">Member</span><span class="sxs-lookup"><span data-stu-id="a1bb8-106">Member</span></span>|<span data-ttu-id="a1bb8-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a1bb8-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="a1bb8-108">Indica que no hay marcas.</span><span class="sxs-lookup"><span data-stu-id="a1bb8-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="a1bb8-109">Indica un `setLastError` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a1bb8-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="a1bb8-110">Indica un `nomangle` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a1bb8-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="a1bb8-111">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a1bb8-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1bb8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1bb8-112">Requirements</span></span>  
 <span data-ttu-id="a1bb8-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1bb8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bb8-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1bb8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1bb8-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1bb8-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1bb8-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bb8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bb8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1bb8-117">See also</span></span>

- [<span data-ttu-id="a1bb8-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a1bb8-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
