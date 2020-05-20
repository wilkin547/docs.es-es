---
title: CustomDumpItem (Estructura)
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616442"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem (Estructura)
Describe un elemento que se va a agregar a un volcado de memoria personalizado en el informe de errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`itemKind`|Valor de [ecustomdumpitemkind (](ecustomdumpitemkind-enumeration.md) que indica el tipo de elemento que se va a agregar.|  
|`pReserved`|No se usa actualmente. Los elementos agregados a la Unión no deben ser mayores que el tamaño del puntero. Si `struct` es necesario, debe asignarlo por separado y apuntar a él.|  
  
## <a name="remarks"></a>Observaciones  
 [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Estructuras de hospedaje](hosting-structures.md)
