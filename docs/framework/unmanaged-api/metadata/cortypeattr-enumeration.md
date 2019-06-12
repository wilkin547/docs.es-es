---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f65c2f74ec5efda027d90b3ffda9a5da5c239122
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025719"
---
# <a name="cortypeattr-enumeration"></a>CorTypeAttr (Enumeración)
Contiene valores que indican los metadatos de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`tdVisibilityMask`|Se utiliza para obtener información de visibilidad del tipo.|  
|`tdNotPublic`|Especifica que el tipo no está en ámbito público.|  
|`tdPublic`|Especifica que el tipo está en ámbito público.|  
|`tdNestedPublic`|Especifica que el tipo se anida con visibilidad pública.|  
|`tdNestedPrivate`|Especifica que el tipo se anida con visibilidad privada.|  
|`tdNestedFamily`|Especifica que el tipo se anida con visibilidad de familia.|  
|`tdNestedAssembly`|Especifica que el tipo se anida con visibilidad de ensamblado.|  
|`tdNestedFamANDAssem`|Especifica que el tipo se anida con visibilidad de familia y ensamblado.|  
|`tdNestedFamORAssem`|Especifica que el tipo se anida con visibilidad de familia o ensamblado.|  
|`tdLayoutMask`|Obtiene información de diseño para el tipo.|  
|`tdAutoLayout`|Especifica que los campos de este tipo se distribuyen automáticamente.|  
|`tdSequentialLayout`|Especifica que los campos de este tipo se disponen secuencialmente.|  
|`tdExplicitLayout`|Especifica el que diseño de los campos se proporciona explícitamente.|  
|`tdClassSemanticsMask`|Obtiene información semántica sobre el tipo.|  
|`tdClass`|Especifica que el tipo es una clase.|  
|`tdInterface`|Especifica que el tipo es una interfaz.|  
|`tdAbstract`|Especifica que el tipo es abstracto.|  
|`tdSealed`|Especifica que no se puede extender el tipo.|  
|`tdSpecialName`|Especifica que el nombre de clase es especial. Su nombre describe cómo.|  
|`tdImport`|Especifica que el tipo se ha importado.|  
|`tdSerializable`|Especifica que el tipo es serializable.|  
|`tdWindowsRuntime`|Especifica que este tipo es un tipo en tiempo de ejecución de Windows.|  
|`tdStringFormatMask`|Obtiene información sobre cómo se codifican y formato de cadenas.|  
|`tdAnsiClass`|Especifica que este tipo interpreta LPTSTR como ANSI.|  
|`tdUnicodeClass`|Especifica que este tipo interpreta LPTSTR como Unicode.|  
|`tdAutoClass`|Especifica que este tipo interpreta LPTSTR automáticamente.|  
|`tdCustomFormatClass`|Especifica que el tipo tiene una codificación no estándar, tal y como especifica `CustomFormatMask`.|  
|`tdCustomFormatMask`|Esta máscara se usa para obtener información de codificación no estándar para la interoperabilidad nativa. El significado de los valores de estos dos bits no está especificado.|  
|`tdBeforeFieldInit`|Especifica que el tipo se debe inicializar antes del primer intento para tener acceso a un campo estático.|  
|`tdForwarder`|Especifica que se exporta el tipo y un reenviador de tipos.|  
|`tdReservedMask`|Common language runtime utiliza internamente esta marca y los indicadores siguientes.|  
|`tdRTSpecialName`|Especifica que common language runtime debe comprobar la codificación de nombres.|  
|`tdHasSecurity`|Especifica que el tipo tiene seguridad asociada a él.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
