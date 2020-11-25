---
title: Función CreateClassEnumWmi (referencia de la API no administrada)
description: La función CreateClassEnumWmi devuelve un enumerador para todas las clases que satisfacen los criterios especificados.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b80954e288f6720c75d0af0b8af083fa4856754
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719741"
---
# <a name="createclassenumwmi-function"></a>Función CreateClassEnumWmi

Devuelve un enumerador para todas las clases que cumplan los criterios de selección especificados.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a>Parámetros

`strSuperclass`\
de Si no es `null` o está en blanco, especifica el nombre de una clase primaria; el enumerador devuelve solo las subclases de esta clase. Si está `null` en blanco y `lFlags` está WBEM_FLAG_SHALLOW, solo devuelve clases de nivel superior (clases sin clase primaria). Si es `null` o está en blanco y `lFlags` es `WBEM_FLAG_DEEP` , devuelve todas las clases del espacio de nombres.

`lFlags`\
de Combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Si se establece, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual. <br/> Si no se establece, la función solo recupera los calificadores almacenados en el espacio de nombres inmediato. |
| `WBEM_FLAG_DEEP` | 0 | La enumeración incluye todas las subclases de la jerarquía, pero no esta clase. |
| `WBEM_FLAG_SHALLOW` | 1 | La enumeración solo incluye instancias puras de esta clase y excluye todas las instancias de subclases que suministran propiedades que no se encuentran en esta clase. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca produce una llamada semisincrónica. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La función devuelve un enumerador de solo avance. Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI conserva los punteros a objetos en la enumeración hasta que se liberan. |

Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para obtener el mejor rendimiento.

`pCtx`\
de Normalmente, este valor es `null` . De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.

`ppEnum`\
enuncia Recibe el puntero al enumerador.

`authLevel`\
de Nivel de autorización.

`impLevel`\
de Nivel de suplantación.

`pCurrentNamespace`\
de Un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) que representa el espacio de nombres actual.

`strUser`\
de El nombre de usuario. Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`strPassword`\
de La contraseña. Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`strAuthority`\
de El nombre de dominio del usuario. Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para ver una o varias de las clases que la función puede devolver. |
| `WBEM_E_FAILED` | 0x80041001 | Error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strSuperClass` no existe. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Es posible que WMI se haya detenido y reiniciado. Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) .

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
