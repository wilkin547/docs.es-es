---
title: CorNativeType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: dd97c479f12e7bdb015b39a802b398ca2b0bcd3f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007642"
---
# <a name="cornativetype-enumeration"></a>CorNativeType (Enumeración)
Contiene valores que describen los tipos nativos no administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|Obsoleto.|  
|`NATIVE_TYPE_VOID`|Obsoleto.|  
|`NATIVE_TYPE_BOOLEAN`|Valor booleano de 4 bytes, donde TRUE es distinto de cero y FALSE es cero.|  
|`NATIVE_TYPE_I1`|Valor entero de 8 bits con signo.|  
|`NATIVE_TYPE_U1`|Valor entero de 8 bits sin signo.|  
|`NATIVE_TYPE_I2`|Valor entero de 16 bits con signo.|  
|`NATIVE_TYPE_U2`|Valor entero de 16 bits sin signo.|  
|`NATIVE_TYPE_I4`|Un valor entero de 32 bits con signo.|  
|`NATIVE_TYPE_U4`|Valor entero de 32 bits sin signo.|  
|`NATIVE_TYPE_I8`|Valor entero de 64 bits con signo.|  
|`NATIVE_TYPE_U8`|Valor entero de 64 bits sin signo.|  
|`NATIVE_TYPE_R4`|Valor numérico de punto flotante de 4 bytes.|  
|`NATIVE_TYPE_R8`|Valor numérico de punto flotante de 8 bytes.|  
|`NATIVE_TYPE_SYSCHAR`|Obsoleto.|  
|`NATIVE_TYPE_VARIANT`|Obsoleto.|  
|`NATIVE_TYPE_CURRENCY`|Tipo COM numérico que corresponde al <xref:System.Decimal> tipo administrado.|  
|`NATIVE_TYPE_PTR`|Obsoleto.|  
|`NATIVE_TYPE_DECIMAL`|Obsoleto.|  
|`NATIVE_TYPE_DATE`|Obsoleto.|  
|`NATIVE_TYPE_BSTR`|Interoperabilidad COM.|  
|`NATIVE_TYPE_LPSTR`|Valor de cadena LPSTR.|  
|`NATIVE_TYPE_LPWSTR`|Valor de cadena LPWSTR.|  
|`NATIVE_TYPE_LPTSTR`|Valor de cadena LPTSTR.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|Valor de cadena fijo definido por el sistema.|  
|`NATIVE_TYPE_OBJECTREF`|Obsoleto.|  
|`NATIVE_TYPE_IUNKNOWN`|Interoperabilidad COM.|  
|`NATIVE_TYPE_IDISPATCH`|Interoperabilidad COM.|  
|`NATIVE_TYPE_STRUCT`|Valor de estructura nativa.|  
|`NATIVE_TYPE_INTF`|Interoperabilidad COM.|  
|`NATIVE_TYPE_SAFEARRAY`|Interoperabilidad COM.|  
|`NATIVE_TYPE_FIXEDARRAY`|Valor de matriz de longitud fija.|  
|`NATIVE_TYPE_INT`|Valor entero de 16 bits con signo nativo.|  
|`NATIVE_TYPE_UINT`|Valor entero de 16 bits sin signo nativo.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|Obsoleto.<br /><br /> Use NATIVE_TYPE_STRUCT.|  
|`NATIVE_TYPE_BYVALSTR`|Interoperabilidad COM.|  
|`NATIVE_TYPE_ANSIBSTR`|Interoperabilidad COM.|  
|`NATIVE_TYPE_TBSTR`|Interoperabilidad COM.<br /><br /> Seleccione BSTR o ANSIBSTR en función de la plataforma.|  
|`NATIVE_TYPE_VARIANTBOOL`|Valor booleano de 2 bytes, donde TRUE es-1 y FALSE es cero.|  
|`NATIVE_TYPE_FUNC`|Puntero de función.|  
|`NATIVE_TYPE_ASANY`|Referencia a cualquier tipo nativo.|  
|`NATIVE_TYPE_ARRAY`|Referencia a una matriz con miembros de un tipo no especificado.|  
|`NATIVE_TYPE_LPSTRUCT`|Un puntero entero de 32 bits a una estructura.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|Un tipo nativo de contador de referencias personalizado.<br /><br /> Debe ir seguido de una cadena con el formato siguiente: "nombre de tipo nativo/nombre de tipo de contador de referencias de 0Custom/cookie de 0Optional/0" o "{GUID de tipo nativo}/0Custom de contador de referencias nombre de tipo/0Optional cookie/0"|  
|`NATIVE_TYPE_ERROR`|Interoperabilidad COM.<br /><br /> Con ELEMENT_TYPE_I4 este tipo se asigna a VT_HRESULT.|  
|`NATIVE_TYPE_IINSPECTABLE`|Tipo nativo `IInspectable` .|  
|`NATIVE_TYPE_HSTRING`|Un nativo `HString` .|  
|`NATIVE_TYPE_MAX`|Valor no válido.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [Enumeraciones para metadatos](metadata-enumerations.md)
