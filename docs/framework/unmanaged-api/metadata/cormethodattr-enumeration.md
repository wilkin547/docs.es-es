---
title: "CorMethodAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodAttr
helpviewer_keywords: CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e144b64664a149115f3047b98267c2f218a76e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr (Enumeración)
Contiene valores que describen las características de un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`mdPrivateScope`|Especifica que el miembro no puede hacer referencia.|  
|`mdPrivate`|Especifica que el miembro solo es accesible para el tipo de elemento primario.|  
|`mdFamANDAssem`|Especifica que el miembro está accesible para los subtipos solo en este ensamblado.|  
|`mdAssem`|Especifica que el miembro es accesible por cualquier usuario en el ensamblado.|  
|`mdFamily`|Especifica que el miembro es accesible sólo mediante tipos y subtipos.|  
|`mdFamORAssem`|Especifica que el miembro es accesible para las clases derivadas y para otros tipos de su ensamblado.|  
|`mdPublic`|Especifica que el miembro está accesible para todos los tipos con acceso al ámbito.|  
|`mdStatic`|Especifica que el miembro está definido como parte del tipo en lugar de como un miembro de una instancia.|  
|`mdFinal`|Especifica que no se puede invalidar el método.|  
|`mdVirtual`|Especifica que el método se puede reemplazar.|  
|`mdHideBySig`|Especifica que el método oculta por nombre y firma, en lugar de simplemente por su nombre.|  
|`mdVtableLayoutMask`|Especifica el diseño de la tabla virtual.|  
|`mdReuseSlot`|Especifica que la ranura usada para este método en la tabla virtual volverá a utilizar. Este es el valor predeterminado.|  
|`mdNewSlot`|Especifica que el método siempre obtiene una nueva ranura en la tabla virtual.|  
|`mdCheckAccessOnOverride`|Especifica que el método puede reemplazarse por los mismos tipos a la que está visible.|  
|`mdAbstract`|Especifica que el método no está implementado.|  
|`mdSpecialName`|Especifica que el método es especial y que su nombre describe cómo.|  
|`mdPinvokeImpl`|Especifica que la implementación del método se reenvía mediante PInvoke.|  
|`mdUnmanagedExport`|Especifica que el método es un método administrado exportado a código no administrado.|  
|`mdReservedMask`|Reservado para uso interno por common language runtime.|  
|`mdRTSpecialName`|Especifica que common language runtime debe comprobar la codificación del nombre del método.|  
|`mdHasSecurity`|Especifica que el método tiene seguridad asociada a él.|  
|`mdRequireSecObject`|Especifica que el método llama a otro método que contiene código de seguridad.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
