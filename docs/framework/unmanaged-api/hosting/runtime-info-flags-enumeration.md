---
description: 'Más información acerca de: enumeración RUNTIME_INFO_FLAGS'
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
ms.openlocfilehash: 54ff62cdee6e940ae9ea8a2ce8ceff99f923d3f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679451"
---
# <a name="runtime_info_flags-enumeration"></a>RUNTIME_INFO_FLAGS (Enumeración)

Contiene valores que indican qué información sobre el Common Language Runtime (CLR) se debe devolver.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Indica que no se debe incluir la información de directorio.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Indica que no se debe incluir la información de versión.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Indica que no se debe mostrar un cuadro de diálogo de error en caso de error.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Indica que se deben invalidar los efectos de llamar a la función [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) con la marca SEM_FAILCRITICALERRORS. Es decir, se debe mostrar un cuadro de diálogo de instalación cuando se produzca un error, en lugar de suprimirse.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Indica una solicitud de información sobre una versión compatible con AMD-64 del motor en tiempo de ejecución.|  
|`RUNTIME_INFO_REQUEST_IA64`|Indica una solicitud de información sobre una versión compatible con IA-64 del Runtime.|  
|`RUNTIME_INFO_REQUEST_X86`|Indica una solicitud de información sobre una versión compatible con x86 del Runtime.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Indica que se debe incluir la información de actualización de la versión.|  
  
## <a name="remarks"></a>Observaciones  

 Las marcas de arquitectura de plataforma siguientes solo se pueden especificar de una en una y no se pueden combinar:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](hosting-enumerations.md)
