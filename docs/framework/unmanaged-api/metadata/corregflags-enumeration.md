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
ms.openlocfilehash: f7b935b8f59e434c9da364be1986dbed654a1efd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445814"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="920b3-102">CorRegFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="920b3-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="920b3-103">Proporciona valores de marca usados para el registro al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="920b3-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="920b3-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="920b3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="920b3-105">Members</span></span>  
  
|<span data-ttu-id="920b3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="920b3-106">Member</span></span>|<span data-ttu-id="920b3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="920b3-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="920b3-108">Especifica que los archivos no deben copiarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="920b3-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="920b3-109">Especifica que el módulo o compuesto es una configuración.</span><span class="sxs-lookup"><span data-stu-id="920b3-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="920b3-110">Especifica que el módulo o el compuesto tiene referencias de clase.</span><span class="sxs-lookup"><span data-stu-id="920b3-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="920b3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="920b3-111">Requirements</span></span>  
 <span data-ttu-id="920b3-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="920b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="920b3-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="920b3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="920b3-114">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="920b3-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="920b3-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="920b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920b3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="920b3-116">See Also</span></span>  
 [<span data-ttu-id="920b3-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="920b3-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
