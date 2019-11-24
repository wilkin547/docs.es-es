---
title: CorDeclSecurity (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: 98183ed02f8821b7c40852de2d040775d30f2518
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443748"
---
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity (Enumeración)
Especifica las acciones de seguridad que se pueden realizar mediante la seguridad declarativa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dclActionMask`|Reservado.|  
|`dclActionNil`|Reservado.|  
|`dclRequest`|Reservado.|  
|`dclDemand`|Todos los autores de llamada de la pila necesitan que se les conceda el permiso especificado por el objeto de permiso actual.|  
|`dclAssert`|The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource|  
|`dclDeny`|The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.|  
|`dclPermitOnly`|Solo se puede acceder a los recursos especificados por este objeto de permiso, aunque al código se le haya concedido permiso de acceso a otros recursos.|  
|`dclLinktimeCheck`|The immediate caller is required to have been granted the specified permission for a given period of time.|  
|`dclInheritanceCheck`|The derived class inheriting another class or overriding a method is required to have been granted the specified permission.|  
|`dclRequestMinimum`|The caller can request for the minimum permissions required for code to run. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclRequestOptional`|The caller can request for additional permissions that are optional (not required to run). Esta solicitud rechaza implícitamente todos los demás permisos no solicitados específicamente. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclRequestRefuse`|The caller's request for permissions that might be misused will not be granted. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclPrejitGrant`|Reservado.|  
|`dclPrejitDenied`|Reservado.|  
|`dclNonCasDemand`|Reservado.|  
|`dclNonCasLinkDemand`|Es necesario que el llamador inmediato haya recibido el permiso especificado.|  
|`dclNonCasInheritance`|Reservado.|  
|`dclLinkDemandChoice`|Reservado.|  
|`dclInheritanceDemandChoice`|Reservado.|  
|`dclDemandChoice`|Reservado.|  
|`dclMaximumValue`|Reservado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
