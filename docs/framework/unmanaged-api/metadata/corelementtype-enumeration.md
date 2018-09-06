---
title: CorElementType (enumeración1)
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5112c3c8d5fef6efada4bffdfa575716503515e6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787719"
---
# <a name="corelementtype-enumeration1"></a>CorElementType (enumeración1)
Especifica un common language runtime <xref:System.Type>, un modificador de tipo o información sobre un tipo en una signatura de tipo de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|Lo utiliza internamente.|  
|`ELEMENT_TYPE_VOID`|Un tipo void.|  
|`ELEMENT_TYPE_BOOLEAN`|Un tipo booleano|  
|`ELEMENT_TYPE_CHAR`|Tipo de carácter.|  
|`ELEMENT_TYPE_I1`|Un entero de 1 byte con signo.|  
|`ELEMENT_TYPE_U1`|Entero de 1 bit sin signo.|  
|`ELEMENT_TYPE_I2`|Un entero con signo de 2 bytes.|  
|`ELEMENT_TYPE_U2`|Entero sin signo de 2 bytes.|  
|`ELEMENT_TYPE_I4`|Un entero de 4 bytes con signo.|  
|`ELEMENT_TYPE_U4`|Un entero de 4 bytes sin signo.|  
|`ELEMENT_TYPE_I8`|Un entero de 8 bytes con signo.|  
|`ELEMENT_TYPE_U8`|Entero sin signo de 8 bytes.|  
|`ELEMENT_TYPE_R4`|Un punto flotante de 4 bytes.|  
|`ELEMENT_TYPE_R8`|Un punto flotante de 8 bytes.|  
|`ELEMENT_TYPE_STRING`|Un tipo System.String.|  
|`ELEMENT_TYPE_PTR`|Un modificador de tipo de puntero.|  
|`ELEMENT_TYPE_BYREF`|Un modificador de tipo de referencia.|  
|`ELEMENT_TYPE_VALUETYPE`|Un modificador de tipo de valor.|  
|`ELEMENT_TYPE_CLASS`|Un modificador de tipo de clase.|  
|`ELEMENT_TYPE_VAR`|Un modificador de tipo de variable de clase.|  
|`ELEMENT_TYPE_ARRAY`|Un modificador de tipo de matriz multidimensional.|  
|`ELEMENT_TYPE_GENERICINST`|Un modificador de tipo para tipos genéricos.|  
|`ELEMENT_TYPE_TYPEDBYREF`|Referencia con tipo.|  
|`ELEMENT_TYPE_I`|Tamaño de un entero nativo.|  
|`ELEMENT_TYPE_U`|Tamaño de un entero nativo sin signo.|  
|`ELEMENT_TYPE_FNPTR`|Un puntero a una función.|  
|`ELEMENT_TYPE_OBJECT`|Un tipo System.Object.|  
|`ELEMENT_TYPE_SZARRAY`|Una sola dimensión, cero modificador de tipo matriz de límite inferior.|  
|`ELEMENT_TYPE_MVAR`|Un modificador de tipo de variable del método.|  
|`ELEMENT_TYPE_CMOD_REQD`|Un lenguaje de C requiere el modificador.|  
|`ELEMENT_TYPE_CMOD_OPT`|Un modificador opcional de lenguaje C.|  
|`ELEMENT_TYPE_INTERNAL`|Lo utiliza internamente.|  
|`ELEMENT_TYPE_MAX`|Tipo no válido.|  
|`ELEMENT_TYPE_MODIFIER`|Lo utiliza internamente.|  
|`ELEMENT_TYPE_SENTINEL`|Un modificador de tipo que es un valor de Centinela para obtener una lista de un número variable de parámetros.|  
|`ELEMENT_TYPE_PINNED`|Lo utiliza internamente.|  
  
## <a name="remarks"></a>Comentarios  
 Los modificadores de tipo forman la base para representar tipos más complejos. Un `CorElementType` se aplica el valor del modificador de tipo para el valor que le sigue inmediatamente en la signatura de tipo. El valor que sigue el `CorElementType` valor del modificador de tipo puede ser un `CorElementType` otro valor, como se especifica en la tabla siguiente, un token de metadatos o el valor de tipo simple.  
  
> [!NOTE]
>  Todos los números (*número*, *argumento Count*, *token de metadatos*, *rango*, *recuento*y *enlazados*) se almacenan como enteros comprimidos. Consulte [estándar ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) en el sitio Web de ECMA para obtener más información.  
  
|Modificador de tipo|Formato|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR < un `CorElementType` valor >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF < un `CorElementType` valor >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE < una `mdTypeDef` token de metadatos >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS < una `mdTypeDef` token de metadatos >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<número >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY < un `CorElementType` valor > \<rango > \<count1 > \<bound1 >... \<countN > \<boundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST < una `mdTypeDef` token de metadatos > \<argumento Count > \<arg1 >... \<argN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<firma completa de la función, incluida la convención de llamada >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY < un `CorElementType` valor >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<número >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ < un `mdTypeRef` o `mdTypeDef` token de metadatos >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT < un `mdTypeRef` o `mdTypeDef` token de metadatos >|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
