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
ms.openlocfilehash: eb6b303fa7569712c854e8dc4e7513d8608e2519
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104967"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="df7bf-102">CorRegFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="df7bf-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="df7bf-103">Proporciona valores de marca usados para el registro al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="df7bf-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df7bf-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="df7bf-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="df7bf-105">Members</span></span>  
  
|<span data-ttu-id="df7bf-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="df7bf-106">Member</span></span>|<span data-ttu-id="df7bf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="df7bf-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="df7bf-108">Especifica que los archivos no deben copiarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="df7bf-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="df7bf-109">Especifica que el módulo o compuesto es una configuración.</span><span class="sxs-lookup"><span data-stu-id="df7bf-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="df7bf-110">Especifica que el módulo o compuesto tiene referencias de clase.</span><span class="sxs-lookup"><span data-stu-id="df7bf-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df7bf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df7bf-111">Requirements</span></span>  
 <span data-ttu-id="df7bf-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df7bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7bf-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="df7bf-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df7bf-114">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df7bf-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="df7bf-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="df7bf-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df7bf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="df7bf-116">See also</span></span>

- [<span data-ttu-id="df7bf-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="df7bf-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
