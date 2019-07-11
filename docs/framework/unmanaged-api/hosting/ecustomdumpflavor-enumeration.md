---
title: ECustomDumpFlavor (Enumeración)
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a416a51f5121f29d373fcfdfa6b0597d9b10ded5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779382"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor (Enumeración)
Contiene valores que indican qué elementos desea incluir en un subconjunto de un montón personalizado de volcado de memoria al informar de errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Especifica que el volcado del montón personalizado debe iniciarse como minivolcado e incluir datos adicionales que se especificó ninguno [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) las instancias que se pasan al mismo método.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Especifica que el volcado del montón personalizado debe recopilar todos los datos de estado de tiempo de ejecución que no se ha asignado dinámicamente.|  
  
## <a name="remarks"></a>Comentarios  
 Un parámetro de tipo `ECustomDumpFlavor` se pasa a la [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ECustomDumpItemKind (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [ICLRErrorReportingManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
