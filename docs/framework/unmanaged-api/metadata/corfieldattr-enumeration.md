---
title: CorFieldAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: 4e40f684cc1578672cb8ff474972ce9cdc39efb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718831"
---
# <a name="corfieldattr-enumeration"></a>CorFieldAttr (Enumeración)

Contiene valores que describen los metadatos de un campo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`fdFieldAccessMask`|Especifica la información de accesibilidad.|  
|`fdPrivateScope`|Indica que no se pueden crear referencias al campo.|  
|`fdPrivate`|Especifica que el campo es accesible únicamente por su tipo primario.|  
|`fdFamANDAssem`|Especifica que el campo es accesible por las clases derivadas de su ensamblado.|  
|`fdAssembly`|Especifica que todos los tipos del ensamblado pueden obtener acceso al campo.|  
|`fdFamily`|Especifica que solo los tipos y las clases derivadas pueden tener acceso al campo.|  
|`fdFamORAssem`|Especifica que el campo es accesible por las clases derivadas y por todos los tipos del ensamblado.|  
|`fdPublic`|Especifica que todos los tipos con visibilidad de este ámbito pueden obtener acceso al campo.|  
|`fdStatic`|Especifica que el campo es un miembro de su tipo en lugar de un miembro de instancia.|  
|`fdInitOnly`|Especifica que el campo no se puede cambiar una vez inicializado.|  
|`fdLiteral`|Especifica que el valor del campo es una constante de tiempo de compilación.|  
|`fdNotSerialized`|Especifica que el campo no se serializa cuando su tipo es remoto.|  
|`fdSpecialName`|Especifica que el campo es especial y que su nombre describe cómo.|  
|`fdPinvokeImpl`|Especifica que la implementación del campo se reenvía a través de PInvoke.|  
|`fdReservedMask`|Reservado para uso interno por el Common Language Runtime.|  
|`fdRTSpecialName`|Especifica que las API internas de metadatos de Common Language Runtime deben comprobar la codificación del nombre.|  
|`fdHasFieldMarshal`|Especifica que el campo contiene información de cálculo de referencias.|  
|`fdHasDefault`|Especifica que el campo tiene un valor predeterminado.|  
|`fdHasFieldRVA`|Especifica que el campo tiene una dirección virtual relativa.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
