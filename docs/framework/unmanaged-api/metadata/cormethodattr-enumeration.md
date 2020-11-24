---
title: CorMethodAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 6c3e721c24da217eaf2e8857377359e1c51b7b59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677029"
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr (Enumeración)

Contiene valores que describen las características de un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`mdMemberAccessMask`|Especifica el acceso a miembros.|  
|`mdPrivateScope`|Especifica que no se puede hacer referencia al miembro.|  
|`mdPrivate`|Especifica que solo el tipo primario puede tener acceso al miembro.|  
|`mdFamANDAssem`|Especifica que solo los subtipos de este ensamblado pueden obtener acceso al miembro.|  
|`mdAssem`|Especifica que el miembro es accesible para cualquier persona del ensamblado.|  
|`mdFamily`|Especifica que solo se puede tener acceso al miembro por tipo y subtipos.|  
|`mdFamORAssem`|Especifica que el miembro es accesible por las clases derivadas y por otros tipos del ensamblado.|  
|`mdPublic`|Especifica que todos los tipos con acceso al ámbito pueden obtener acceso al miembro.|  
|`mdStatic`|Especifica que el miembro se define como parte del tipo en lugar de como miembro de una instancia de.|  
|`mdFinal`|Especifica que el método no se puede invalidar.|  
|`mdVirtual`|Especifica que el método se puede invalidar.|  
|`mdHideBySig`|Especifica que el método se oculta por nombre y firma, en lugar de simplemente por nombre.|  
|`mdVtableLayoutMask`|Especifica el diseño de la tabla virtual.|  
|`mdReuseSlot`|Especifica que se reutilizará la ranura utilizada para este método en la tabla virtual. Este es el valor predeterminado.|  
|`mdNewSlot`|Especifica que el método siempre obtiene una nueva ranura en la tabla virtual.|  
|`mdCheckAccessOnOverride`|Especifica que el método puede ser invalidado por los mismos tipos en los que está visible.|  
|`mdAbstract`|Especifica que el método no está implementado.|  
|`mdSpecialName`|Especifica que el método es especial y que su nombre describe cómo.|  
|`mdPinvokeImpl`|Especifica que la implementación del método se reenvía mediante PInvoke.|  
|`mdUnmanagedExport`|Especifica que el método es un método administrado exportado a código no administrado.|  
|`mdReservedMask`|Reservado para uso interno por el Common Language Runtime.|  
|`mdRTSpecialName`|Especifica que el Common Language Runtime debe comprobar la codificación del nombre del método.|  
|`mdHasSecurity`|Especifica que el método tiene seguridad asociada.|  
|`mdRequireSecObject`|Especifica que el método llama a otro método que contiene código de seguridad.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
