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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5409d1b89ba3e50c4ae17ed5aa6bf063cf6c93cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136973"
---
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity (Enumeración)
Especifica las acciones de seguridad que se pueden realizar mediante la seguridad declarativa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`dclAssert`|El código de llamada puede tener acceso al recurso identificado por el objeto de permiso actual, aunque los llamadores situados en la pila no tienen permiso para acceder al recurso|  
|`dclDeny`|La capacidad de tener acceso al recurso especificado por el objeto de permiso actual se deniega a los llamadores, incluso si se les ha concedido permiso para acceder a él.|  
|`dclPermitOnly`|Solo se puede acceder a los recursos especificados por este objeto de permiso, aunque al código se le haya concedido permiso de acceso a otros recursos.|  
|`dclLinktimeCheck`|El llamador inmediato es necesario tener concedido el permiso especificado para un determinado período de tiempo.|  
|`dclInheritanceCheck`|La clase derivada hereda de otra clase o invalida un método es necesaria tener concedido el permiso especificado.|  
|`dclRequestMinimum`|El llamador puede solicitar los permisos mínimos necesarios para que ejecutar código. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclRequestOptional`|El llamador puede solicitar permisos adicionales que son opcionales (no es necesario para ejecutar). Esta solicitud rechaza implícitamente todos los demás permisos no solicitados específicamente. Esta acción solo se puede usar en el ámbito del ensamblado.|  
|`dclRequestRefuse`|No se concederá la solicitud del llamador para los permisos que se puedan usar indebidamente. Esta acción solo se puede usar en el ámbito del ensamblado.|  
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
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
