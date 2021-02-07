---
description: 'Más información sobre: enumeración Cortypeattr ('
title: CorTypeAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
ms.openlocfilehash: d4f7d25ce8ead945790defae800b7a45dc88bc38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721173"
---
# <a name="cortypeattr-enumeration"></a>CorTypeAttr (Enumeración)

Contiene valores que indican los metadatos de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`tdVisibilityMask`|Se usa para la información de visibilidad del tipo.|  
|`tdNotPublic`|Especifica que el tipo no está en el ámbito público.|  
|`tdPublic`|Especifica que el tipo está en el ámbito público.|  
|`tdNestedPublic`|Especifica que el tipo se anida con visibilidad pública.|  
|`tdNestedPrivate`|Especifica que el tipo está anidado con visibilidad privada.|  
|`tdNestedFamily`|Especifica que el tipo está anidado con visibilidad de la familia.|  
|`tdNestedAssembly`|Especifica que el tipo está anidado con visibilidad de ensamblado.|  
|`tdNestedFamANDAssem`|Especifica que el tipo se anida con visibilidad de familia y ensamblado.|  
|`tdNestedFamORAssem`|Especifica que el tipo se anida con visibilidad de familia o ensamblado.|  
|`tdLayoutMask`|Obtiene información de diseño para el tipo.|  
|`tdAutoLayout`|Especifica que los campos de este tipo se colocan automáticamente.|  
|`tdSequentialLayout`|Especifica que los campos de este tipo se disponen secuencialmente.|  
|`tdExplicitLayout`|Especifica que el diseño de campo se proporciona explícitamente.|  
|`tdClassSemanticsMask`|Obtiene información semántica sobre el tipo.|  
|`tdClass`|Especifica que el tipo es una clase.|  
|`tdInterface`|Especifica que el tipo es una interfaz.|  
|`tdAbstract`|Especifica que el tipo es abstracto.|  
|`tdSealed`|Especifica que el tipo no se puede extender.|  
|`tdSpecialName`|Especifica que el nombre de la clase es especial. Su nombre describe cómo.|  
|`tdImport`|Especifica que el tipo se ha importado.|  
|`tdSerializable`|Especifica que el tipo es serializable.|  
|`tdWindowsRuntime`|Especifica que este tipo es un tipo de Windows Runtime.|  
|`tdStringFormatMask`|Obtiene información sobre cómo se codifican y formatean las cadenas.|  
|`tdAnsiClass`|Especifica que este tipo interpreta LPTSTR como ANSI.|  
|`tdUnicodeClass`|Especifica que este tipo interpreta LPTSTR como Unicode.|  
|`tdAutoClass`|Especifica que este tipo interpreta LPTSTR automáticamente.|  
|`tdCustomFormatClass`|Especifica que el tipo tiene una codificación no estándar, tal y como especifica `CustomFormatMask` .|  
|`tdCustomFormatMask`|Use esta máscara para obtener información de codificación no estándar para la interoperabilidad nativa. El significado de los valores de estos dos bits no se especifica.|  
|`tdBeforeFieldInit`|Especifica que el tipo se debe inicializar antes del primer intento de obtener acceso a un campo estático.|  
|`tdForwarder`|Especifica que el tipo se exporta y un reenviador de tipos.|  
|`tdReservedMask`|El Common Language Runtime utiliza internamente esta marca y las marcas siguientes.|  
|`tdRTSpecialName`|Especifica que el Common Language Runtime debe comprobar la codificación del nombre.|  
|`tdHasSecurity`|Especifica que el tipo tiene seguridad asociada.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
