---
title: "RUNTIME_INFO_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d050972857ba652ae0b40727260f681c383208b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="11c4b-102">RUNTIME_INFO_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="11c4b-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="11c4b-103">Contiene valores que indican qué información acerca de common language runtime (CLR) se debe devolver.</span><span class="sxs-lookup"><span data-stu-id="11c4b-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11c4b-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="11c4b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="11c4b-105">Members</span></span>  
  
|<span data-ttu-id="11c4b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="11c4b-106">Member</span></span>|<span data-ttu-id="11c4b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c4b-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="11c4b-108">Indica que no debe incluirse la información del directorio.</span><span class="sxs-lookup"><span data-stu-id="11c4b-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="11c4b-109">Indica que no debe incluirse la información de versión.</span><span class="sxs-lookup"><span data-stu-id="11c4b-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="11c4b-110">Indica que no se debe mostrar un cuadro de diálogo de error en caso de error.</span><span class="sxs-lookup"><span data-stu-id="11c4b-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="11c4b-111">Indica que los efectos de la llamada a la [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) se debe invalidar la función con la marca SEM_FAILCRITICALERRORS.</span><span class="sxs-lookup"><span data-stu-id="11c4b-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="11c4b-112">Es decir, se debería mostrar un cuadro de diálogo de instalación en caso de error, en lugar de que se va a suprimir.</span><span class="sxs-lookup"><span data-stu-id="11c4b-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="11c4b-113">Indica una solicitud para obtener información acerca de una versión compatible con AMD-64 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11c4b-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="11c4b-114">Indica una solicitud para obtener información acerca de una versión compatible con IA-64 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11c4b-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="11c4b-115">Indica una solicitud para obtener información acerca de una versión compatible de x86 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11c4b-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="11c4b-116">Indica que se debe incluir información de actualización de versión.</span><span class="sxs-lookup"><span data-stu-id="11c4b-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c4b-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11c4b-117">Remarks</span></span>  
 <span data-ttu-id="11c4b-118">Los siguientes indicadores de arquitectura de plataforma se pueden especificar sólo de uno en uno y no se pueden combinar:</span><span class="sxs-lookup"><span data-stu-id="11c4b-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="11c4b-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="11c4b-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="11c4b-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="11c4b-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="11c4b-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="11c4b-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c4b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11c4b-122">Requirements</span></span>  
 <span data-ttu-id="11c4b-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11c4b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c4b-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11c4b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11c4b-125">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11c4b-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11c4b-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11c4b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c4b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="11c4b-127">See Also</span></span>  
 [<span data-ttu-id="11c4b-128">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="11c4b-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
