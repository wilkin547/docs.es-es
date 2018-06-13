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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f742d219d603488bbade091f7a8192785d3e84f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433101"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem (Estructura)
Describe un elemento que se va a agregar a un volcado personalizado en informes de errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`itemKind`|Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valor que indica el tipo de elemento que se va a agregar.|  
|`pReserved`|No se están utilizando. Los elementos agregados a la unión deben ser no mayores que el tamaño del puntero. Si un `struct` es necesario, debe asignar de forma independiente y apunte a ella.|  
  
## <a name="remarks"></a>Comentarios  
 [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.idl  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
