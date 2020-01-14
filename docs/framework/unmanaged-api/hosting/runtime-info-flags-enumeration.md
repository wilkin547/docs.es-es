---
title: RUNTIME_INFO_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 9d505b917c343c40c7fa2a7aecf3466578ae0a8d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936641"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="1c7a7-102">RUNTIME_INFO_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1c7a7-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="1c7a7-103">Contiene valores que indican qué información sobre el Common Language Runtime (CLR) se debe devolver.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c7a7-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="1c7a7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1c7a7-105">Members</span></span>  
  
|<span data-ttu-id="1c7a7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1c7a7-106">Member</span></span>|<span data-ttu-id="1c7a7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c7a7-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="1c7a7-108">Indica que no se debe incluir la información de directorio.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="1c7a7-109">Indica que no se debe incluir la información de versión.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="1c7a7-110">Indica que no se debe mostrar un cuadro de diálogo de error en caso de error.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="1c7a7-111">Indica que se deben invalidar los efectos de llamar a la función [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) con la marca SEM_FAILCRITICALERRORS.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="1c7a7-112">Es decir, se debe mostrar un cuadro de diálogo de instalación cuando se produzca un error, en lugar de suprimirse.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="1c7a7-113">Indica una solicitud de información sobre una versión compatible con AMD-64 del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="1c7a7-114">Indica una solicitud de información sobre una versión compatible con IA-64 del Runtime.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="1c7a7-115">Indica una solicitud de información sobre una versión compatible con x86 del Runtime.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="1c7a7-116">Indica que se debe incluir la información de actualización de la versión.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c7a7-117">Notas</span><span class="sxs-lookup"><span data-stu-id="1c7a7-117">Remarks</span></span>  
 <span data-ttu-id="1c7a7-118">Las marcas de arquitectura de plataforma siguientes solo se pueden especificar de una en una y no se pueden combinar:</span><span class="sxs-lookup"><span data-stu-id="1c7a7-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="1c7a7-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="1c7a7-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="1c7a7-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="1c7a7-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="1c7a7-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="1c7a7-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7a7-122">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1c7a7-122">Requirements</span></span>  
 <span data-ttu-id="1c7a7-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c7a7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7a7-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1c7a7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c7a7-125">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1c7a7-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c7a7-126">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7a7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7a7-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c7a7-127">See also</span></span>

- [<span data-ttu-id="1c7a7-128">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="1c7a7-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
