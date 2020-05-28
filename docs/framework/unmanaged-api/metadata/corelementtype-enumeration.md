---
title: CorElementType (Enumeración)
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
ms.openlocfilehash: 25fb3278e576ebe4a538379918e868b2e5f87911
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007876"
---
# <a name="corelementtype-enumeration"></a>CorElementType (Enumeración)

Especifica un Common Language Runtime <xref:System.Type> , un modificador de tipo o información sobre un tipo en una firma de tipo de metadatos.

## <a name="syntax"></a>Sintaxis

```cpp
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
|`ELEMENT_TYPE_END`|Utilizado de forma interna.|
|`ELEMENT_TYPE_VOID`|Un tipo void.|
|`ELEMENT_TYPE_BOOLEAN`|Un tipo booleano|
|`ELEMENT_TYPE_CHAR`|Tipo de carácter.|
|`ELEMENT_TYPE_I1`|Entero de 1 byte con signo.|
|`ELEMENT_TYPE_U1`|Entero de 1 bit sin signo.|
|`ELEMENT_TYPE_I2`|Entero de 2 bytes con signo.|
|`ELEMENT_TYPE_U2`|Entero de 2 bytes sin signo.|
|`ELEMENT_TYPE_I4`|Entero de 4 bytes con signo.|
|`ELEMENT_TYPE_U4`|Entero de 4 bytes sin signo.|
|`ELEMENT_TYPE_I8`|Entero de 8 bytes con signo.|
|`ELEMENT_TYPE_U8`|Entero de 8 bytes sin signo.|
|`ELEMENT_TYPE_R4`|Punto flotante de 4 bytes.|
|`ELEMENT_TYPE_R8`|Punto flotante de 8 bytes.|
|`ELEMENT_TYPE_STRING`|Tipo System. String.|
|`ELEMENT_TYPE_PTR`|Modificador de tipo de puntero.|
|`ELEMENT_TYPE_BYREF`|Modificador de tipo de referencia.|
|`ELEMENT_TYPE_VALUETYPE`|Modificador de tipo de valor.|
|`ELEMENT_TYPE_CLASS`|Modificador de tipo de clase.|
|`ELEMENT_TYPE_VAR`|Modificador de tipo variable de clase.|
|`ELEMENT_TYPE_ARRAY`|Modificador de tipo de matriz multidimensional.|
|`ELEMENT_TYPE_GENERICINST`|Modificador de tipo para tipos genéricos.|
|`ELEMENT_TYPE_TYPEDBYREF`|Referencia con tipo.|
|`ELEMENT_TYPE_I`|Tamaño de un entero nativo.|
|`ELEMENT_TYPE_U`|Tamaño de un entero nativo sin signo.|
|`ELEMENT_TYPE_FNPTR`|Puntero a una función.|
|`ELEMENT_TYPE_OBJECT`|Tipo System. Object.|
|`ELEMENT_TYPE_SZARRAY`|Modificador de tipo de matriz unidimensional y de límite inferior.|
|`ELEMENT_TYPE_MVAR`|Modificador de tipo variable de método.|
|`ELEMENT_TYPE_CMOD_REQD`|Modificador obligatorio en el lenguaje C.|
|`ELEMENT_TYPE_CMOD_OPT`|Modificador opcional del lenguaje C.|
|`ELEMENT_TYPE_INTERNAL`|Utilizado de forma interna.|
|`ELEMENT_TYPE_MAX`|Tipo no válido.|
|`ELEMENT_TYPE_MODIFIER`|Utilizado de forma interna.|
|`ELEMENT_TYPE_SENTINEL`|Modificador de tipo que es un centinela para una lista de un número variable de parámetros.|
|`ELEMENT_TYPE_PINNED`|Utilizado de forma interna.|

## <a name="remarks"></a>Comentarios

Los modificadores de tipo constituyen la base para representar tipos más complejos. Un `CorElementType` valor de modificador de tipo se aplica al valor que lo sigue inmediatamente en la signatura de tipo. El valor que sigue al `CorElementType` valor del modificador de tipo puede ser un `CorElementType` valor de tipo simple, un token de metadatos u otro valor, como se especifica en la tabla siguiente.

> [!NOTE]
> Todos los números *(número, número*de *argumentos*, *token de metadatos*, *rango*, *recuento*y *enlazado*) se almacenan como enteros comprimidos. Consulte el [estándar ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) en el sitio web de ECMA para obtener más información.

|Modificador de tipo|Formato|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR\<a `CorElementType` value>|
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF\<a `CorElementType` value>|
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE\<an `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS\<an `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR\<number>|
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN>\<boundN>|
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ...\<argN>|
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR\<complete signature for the function, including calling convention>|
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY\<a `CorElementType` value>|
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR\<number>|
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT\<a `mdTypeRef` or `mdTypeDef` metadata token>|

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorHdr. h

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
