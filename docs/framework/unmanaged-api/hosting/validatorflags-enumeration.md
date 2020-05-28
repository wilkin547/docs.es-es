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
ms.openlocfilehash: d5eb225241f597baf7a0a5584f4aaf8bf8411ea2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009475"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags (Enumeración)
Contiene valores que indican el tipo de validación que se debe realizar en una llamada al método [ICLRValidator:: Validate](iclrvalidator-validate-method.md) .  
  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Especifica que solo se debe validar el lenguaje intermedio de Microsoft (MSIL) del archivo ejecutable.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Especifica que solo se debe validar el formato del archivo ejecutable.|  
|`VALIDATOR_EXTRA_VERBOSE`|Especifica que se deben realizar y informar de todos los tipos de validación.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Especifica que no se debe validar el formato del archivo ejecutable.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Especifica que los mensajes de error de validación deben incluir las líneas de código fuente que provocan errores de validación. Este valor de campo no es válido en la versión .NET Framework 2,0.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** IValidator. idl, IValidator. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRErrorReportingManager (Interfaz)](iclrerrorreportingmanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
