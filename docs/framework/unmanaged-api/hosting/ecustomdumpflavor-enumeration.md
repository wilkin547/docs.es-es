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
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616286"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor (Enumeración)
Contiene valores que indican qué elementos se van a incluir en un subconjunto personalizado de un volcado del montón cuando se notifican errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Especifica que el volcado del montón personalizado debe iniciarse como minivolcado e incluir los datos adicionales especificados por las instancias de [customdumpitem (](customdumpitem-structure.md) que se hayan pasado al mismo método.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Especifica que el volcado del montón personalizado debe recopilar todos los datos de estado de tiempo de ejecución que no se asignaron dinámicamente.|  
  
## <a name="remarks"></a>Observaciones  
 Un parámetro de tipo `ECustomDumpFlavor` se pasa al método [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ECustomDumpItemKind (Enumeración)](ecustomdumpitemkind-enumeration.md)
- [ICLRErrorReportingManager (Interfaz)](iclrerrorreportingmanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
