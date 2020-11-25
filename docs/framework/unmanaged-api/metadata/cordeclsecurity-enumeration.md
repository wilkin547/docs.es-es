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
ms.openlocfilehash: dd599ce8c63fa94e1a18b4e2d18fa334238728bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718883"
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
|`dclAssert`|El código de llamada puede tener acceso al recurso identificado por el objeto de permiso actual, incluso si los autores de la llamada situados en una posición más alta de la pila no tienen permiso para obtener acceso al recurso.|  
|`dclDeny`|La capacidad de tener acceso al recurso especificado por el objeto de permiso actual se deniega a los llamadores, incluso si se les ha concedido permiso de acceso.|  
|`dclPermitOnly`|Solo se puede acceder a los recursos especificados por este objeto de permiso, aunque al código se le haya concedido permiso de acceso a otros recursos.|  
|`dclLinktimeCheck`|Se requiere que el llamador inmediato tenga concedido el permiso especificado para un período de tiempo determinado.|  
|`dclInheritanceCheck`|La clase derivada que hereda otra clase o invalida un método debe tener concedido el permiso especificado.|  
|`dclRequestMinimum`|El autor de la llamada puede solicitar los permisos mínimos necesarios para que se ejecute el código. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclRequestOptional`|El autor de la llamada puede solicitar permisos adicionales que son opcionales (no es necesario ejecutar). Esta solicitud rechaza implícitamente todos los demás permisos no solicitados específicamente. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclRequestRefuse`|No se concederá la solicitud del llamador de los permisos que se puedan usar inconvenientemente. Esta acción solo se puede usar en el ámbito del ensamblado.|  
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

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
