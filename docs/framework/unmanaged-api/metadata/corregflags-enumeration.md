---
title: "CorRegFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRegFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRegFlags
helpviewer_keywords: CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8118de9f4fc6a4f2820b88685b9b87c498328b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="3c33d-102">CorRegFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3c33d-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="3c33d-103">Proporciona valores de marca usados para el registro al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="3c33d-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c33d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c33d-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3c33d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3c33d-105">Members</span></span>  
  
|<span data-ttu-id="3c33d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3c33d-106">Member</span></span>|<span data-ttu-id="3c33d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c33d-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="3c33d-108">Especifica que los archivos no deben copiarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="3c33d-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="3c33d-109">Especifica que el módulo o compuesto es una configuración.</span><span class="sxs-lookup"><span data-stu-id="3c33d-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="3c33d-110">Especifica que el módulo o el compuesto tiene referencias de clase.</span><span class="sxs-lookup"><span data-stu-id="3c33d-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c33d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c33d-111">Requirements</span></span>  
 <span data-ttu-id="3c33d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c33d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c33d-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c33d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c33d-114">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c33d-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c33d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c33d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c33d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c33d-116">See Also</span></span>  
 [<span data-ttu-id="3c33d-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="3c33d-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
