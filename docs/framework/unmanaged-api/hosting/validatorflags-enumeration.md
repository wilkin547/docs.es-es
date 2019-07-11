---
title: ValidatorFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5f38231eb6a5911527c21ee3304fc77cfcf8e90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776522"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags (Enumeración)
Contiene valores que indican el tipo de validación que se debe realizar en una llamada a la [ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Especifica que solo el lenguaje intermedio de Microsoft (MSIL) en el archivo ejecutable se debe validar.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Especifica que sólo el formato del archivo ejecutable se debe validar.|  
|`VALIDATOR_EXTRA_VERBOSE`|Especifica que deben realizarse y notifican en todos los tipos de validación.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Especifica que no se debe validar el formato del archivo ejecutable.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Especifica que los mensajes de error de validación deben incluir las líneas de código fuente que generan un error de validación. Este valor de campo no es válido en la versión 2.0 de .NET Framework.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: IValidator.idl, IValidator.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRErrorReportingManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
