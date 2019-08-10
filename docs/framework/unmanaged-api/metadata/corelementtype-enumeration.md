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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6057bd48ff4fe3f852f82de2bab972d95fef138c
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868567"
---
# <a name="corelementtype-enumeration"></a>CorElementType (Enumeración)

Especifica un Common Language Runtime <xref:System.Type>, un modificador de tipo o información sobre un tipo en una firma de tipo de metadatos.

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

|Member|DESCRIPCIÓN|
|------------|-----------------|
|`ELEMENT_TYPE_END`|Se usa internamente.|
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
|`ELEMENT_TYPE_INTERNAL`|Se usa internamente.|
|`ELEMENT_TYPE_MAX`|Tipo no válido.|
|`ELEMENT_TYPE_MODIFIER`|Se usa internamente.|
|`ELEMENT_TYPE_SENTINEL`|Modificador de tipo que es un centinela para una lista de un número variable de parámetros.|
|`ELEMENT_TYPE_PINNED`|Se usa internamente.|

## <a name="remarks"></a>Comentarios

Los modificadores de tipo constituyen la base para representar tipos más complejos. Un `CorElementType` valor de modificador de tipo se aplica al valor que lo sigue inmediatamente en la signatura de tipo. El valor que sigue al `CorElementType` valor del modificador de tipo puede `CorElementType` ser un valor de tipo simple, un token de metadatos u otro valor, como se especifica en la tabla siguiente.

> [!NOTE]
> Todos los números *(número, número*de *argumentos*, *token*de metadatos, *rango*, recuento y *enlazado*) se almacenan como enteros comprimidos. Consulte el [estándar ECMA-335-Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) en el sitio web de ECMA para obtener más información.

|Modificador de tipo|Formato|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR \< un`CorElementType` valor >|
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF \< un`CorElementType` valor >|
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE \< un`mdTypeDef` token de metadatos >|
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS \< un`mdTypeDef` token de metadatos >|
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<número >|
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY \<un `CorElementType` valor > \<rango > \<count1 >\<bound1 >... countn > \<boundn> \<|
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST \< \< \<un `mdTypeDef` token de metadatos > recuento de argumentos > arg1 >... \<> argn|
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<completar firma para la función, incluida la Convención de llamada >|
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY \< un`CorElementType` valor >|
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<número >|
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_\< `mdTypeDef` un `mdTypeRef` token de metadatos o >|
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT \< `mdTypeDef` un `mdTypeRef` token de metadatos o >|

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: CorHdr. h

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
