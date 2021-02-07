---
description: 'Más información acerca de: estructura Customdumpitem ('
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
ms.openlocfilehash: 9bd7b2bb59675bc01e24dc6e6d0ce524f3d35466
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716905"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`itemKind`|Valor de [ecustomdumpitemkind (](ecustomdumpitemkind-enumeration.md) que indica el tipo de elemento que se va a agregar.|  
|`pReserved`|No se usa actualmente. Los elementos agregados a la Unión no deben ser mayores que el tamaño del puntero. Si `struct` es necesario, debe asignarlo por separado y apuntar a él.|  
  
## <a name="remarks"></a>Observaciones  

 [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](hosting-structures.md)
