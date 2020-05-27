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
ms.openlocfilehash: 9211af4726617598f3dd8772383cade6368e6c08
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007629"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="b4976-102">CorNativeLinkFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b4976-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="b4976-103">Proporciona valores de marca que el vinculador usa al vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="b4976-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4976-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4976-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b4976-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b4976-105">Members</span></span>  
  
|<span data-ttu-id="b4976-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b4976-106">Member</span></span>|<span data-ttu-id="b4976-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4976-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="b4976-108">Indica que no hay marcas.</span><span class="sxs-lookup"><span data-stu-id="b4976-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="b4976-109">Indica una `setLastError` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b4976-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="b4976-110">Indica una `nomangle` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b4976-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="b4976-111">No se usa.</span><span class="sxs-lookup"><span data-stu-id="b4976-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4976-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4976-112">Requirements</span></span>  
 <span data-ttu-id="b4976-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4976-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4976-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b4976-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4976-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b4976-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4976-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4976-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4976-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4976-117">See also</span></span>

- [<span data-ttu-id="b4976-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b4976-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
