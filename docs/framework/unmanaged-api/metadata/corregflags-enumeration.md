---
title: CorRegFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf2a1bca6115902d96f72c19dc469d0a1c8588cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756219"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="cc8d2-102">CorRegFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cc8d2-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="cc8d2-103">Proporciona valores de marca usados para el registro al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="cc8d2-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc8d2-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cc8d2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cc8d2-105">Members</span></span>  
  
|<span data-ttu-id="cc8d2-106">Member</span><span class="sxs-lookup"><span data-stu-id="cc8d2-106">Member</span></span>|<span data-ttu-id="cc8d2-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cc8d2-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="cc8d2-108">Especifica que los archivos no deben copiarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="cc8d2-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="cc8d2-109">Especifica que el módulo o compuesto es una configuración.</span><span class="sxs-lookup"><span data-stu-id="cc8d2-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="cc8d2-110">Especifica que el módulo o compuesto tiene referencias de clase.</span><span class="sxs-lookup"><span data-stu-id="cc8d2-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc8d2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc8d2-111">Requirements</span></span>  
 <span data-ttu-id="cc8d2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc8d2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8d2-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="cc8d2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc8d2-114">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc8d2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc8d2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc8d2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8d2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc8d2-116">See also</span></span>

- [<span data-ttu-id="cc8d2-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="cc8d2-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
