---
title: CorElementType Enumeration1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorElementType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorElementType
helpviewer_keywords: CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8932e295aa1a6c6cf961e7b3a218e76984da02cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corelementtype-enumeration1"></a>CorElementType Enumeration1
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
|`ELEMENT_TYPE_END`|Se utiliza internamente.|  
|`ELEMENT_TYPE_VOID`|Un tipo void.|  
|`ELEMENT_TYPE_BOOLEAN`|Un tipo booleano|  
|`ELEMENT_TYPE_CHAR`|Tipo de carácter.|  
|`ELEMENT_TYPE_I1`|Un entero de 1 byte con signo.|  
|`ELEMENT_TYPE_U1`|Entero de 1 bit sin signo.|  
|`ELEMENT_TYPE_I2`|Un entero de 2 bytes con signo.|  
|`ELEMENT_TYPE_U2`|Un entero de 2 bytes sin signo.|  
|`ELEMENT_TYPE_I4`|Un entero de 4 bytes con signo.|  
|`ELEMENT_TYPE_U4`|Un entero de 4 bytes sin signo.|  
|`ELEMENT_TYPE_I8`|Un entero de 8 bits con signo.|  
|`ELEMENT_TYPE_U8`|Un entero de 8 bits sin signo.|  
|`ELEMENT_TYPE_R4`|Un punto flotante de 4 bytes.|  
|`ELEMENT_TYPE_R8`|Un punto flotante de 8 bytes.|  
|`ELEMENT_TYPE_STRING`|Un tipo System.String.|  
|`ELEMENT_TYPE_PTR`|Un modificador de tipo de puntero.|  
|`ELEMENT_TYPE_BYREF`|Un modificador de tipo de referencia.|  
|`ELEMENT_TYPE_VALUETYPE`|Un modificador de tipo de valor.|  
|`ELEMENT_TYPE_CLASS`|Un modificador de tipo de clase.|  
|`ELEMENT_TYPE_VAR`|Un modificador de tipo de variable de clase.|  
|`ELEMENT_TYPE_ARRAY`|Un modificador de tipo matriz multidimensional.|  
|`ELEMENT_TYPE_GENERICINST`|Un modificador de tipo para tipos genéricos.|  
|`ELEMENT_TYPE_TYPEDBYREF`|Referencia con tipo.|  
|`ELEMENT_TYPE_I`|Tamaño de un entero nativo.|  
|`ELEMENT_TYPE_U`|Tamaño de un entero nativo sin signo.|  
|`ELEMENT_TYPE_FNPTR`|Un puntero a una función.|  
|`ELEMENT_TYPE_OBJECT`|Un tipo System.Object.|  
|`ELEMENT_TYPE_SZARRAY`|Una sola dimensión, cero modificador de tipo de matriz de límite inferior.|  
|`ELEMENT_TYPE_MVAR`|Un modificador de tipo de variable de método.|  
|`ELEMENT_TYPE_CMOD_REQD`|Modificador requerido por el lenguaje c.|  
|`ELEMENT_TYPE_CMOD_OPT`|Un modificador opcional de lenguaje C.|  
|`ELEMENT_TYPE_INTERNAL`|Se utiliza internamente.|  
|`ELEMENT_TYPE_MAX`|Tipo no válido.|  
|`ELEMENT_TYPE_MODIFIER`|Se utiliza internamente.|  
|`ELEMENT_TYPE_SENTINEL`|Un modificador de tipo que es un Centinela para obtener una lista de un número variable de parámetros.|  
|`ELEMENT_TYPE_PINNED`|Se utiliza internamente.|  
  
## <a name="remarks"></a>Comentarios  
 Los modificadores de tipo forman la base para representar tipos más complejos. Un `CorElementType` valor del modificador de tipo se aplica al valor que le sigue inmediatamente en la signatura de tipo. El valor que sigue a la `CorElementType` valor de modificador de tipo puede ser un `CorElementType` valor de tipo simple, un token de metadatos u otro valor, como se especifica en la tabla siguiente.  
  
> [!NOTE]
>  Todos los números (*número*, *argumento Count*, *token de metadatos*, *rango*, *recuento*y *enlazados*) se almacenan como enteros comprimidos. Vea [estándar ECMA-335: Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) en el sitio Web de ECMA para obtener más información.  
  
|Modificador de tipo|Formato|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR < un `CorElementType` valor >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF < un `CorElementType` valor >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE < una `mdTypeDef` token de metadatos >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS < una `mdTypeDef` token de metadatos >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<número >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY < una `CorElementType` valor > \<rango > \<count1 > \<bound1 >... \<countN > \<boundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST < una `mdTypeDef` token de metadatos > \<argumento Count > \<arg1 >... \<argN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<firma completa de la función, incluida la convención de llamada >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY < un `CorElementType` valor >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<número >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ < una `mdTypeRef` o `mdTypeDef` token de metadatos >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT < una `mdTypeRef` o `mdTypeDef` token de metadatos >|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
