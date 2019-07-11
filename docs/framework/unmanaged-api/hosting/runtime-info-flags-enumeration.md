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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bf3a0507f9f7d4d622163a55fc9c45b4a4dd0a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781145"
---
# <a name="runtimeinfoflags-enumeration"></a>RUNTIME_INFO_FLAGS (Enumeración)
Contiene valores que indican qué información acerca de common language runtime (CLR) se debe devolver.  
  
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
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Indica que no debe incluirse la información de directorio.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Indica que no debe incluirse la información de versión.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Indica que no se debe mostrar un cuadro de diálogo de error tras un error.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Indica que los efectos de la llamada a la [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) se debe invalidar la función con la marca SEM_FAILCRITICALERRORS. Es decir, se debe mostrar un cuadro de diálogo de instalación en caso de error, en lugar de que se va a suprimir.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Indica una solicitud para obtener información acerca de una versión compatible con AMD-64 del tiempo de ejecución.|  
|`RUNTIME_INFO_REQUEST_IA64`|Indica una solicitud para obtener información acerca de una versión compatible con IA-64 del tiempo de ejecución.|  
|`RUNTIME_INFO_REQUEST_X86`|Indica una solicitud para obtener información acerca de una versión compatible con x86 del tiempo de ejecución.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Indica que se debe incluir información de actualización de versión.|  
  
## <a name="remarks"></a>Comentarios  
 Los siguientes indicadores de arquitectura de plataforma pueden ser solo uno especificado a la vez y no se pueden combinar:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
