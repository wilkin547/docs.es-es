---
title: Función CreateClassEnumWmi (referencia de API no administrada)
description: La función CreateClassEnumWmi devuelve un enumerador para todas las clases que cumplen los criterios especificados.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4d2c2bd28640d0ac7124f8e0864e9e72fb1eb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935634"
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
[in] Si no `null` o en blanco, especifica el nombre de una clase primaria; el enumerador devuelve solo las subclases de esta clase. Si es `null` o en blanco y `lFlags` es WBEM_FLAG_SHALLOW, se devuelve solo clases de nivel superior (las clases con ninguna clase de elemento primario). Si es `null` o en blanco y `lFlags` es `WBEM_FLAG_DEEP`, devuelve todas las clases del espacio de nombres.

`lFlags`\
[in] Una combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Si el conjunto, la función recupera los calificadores almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual. <br/> Si no la función de conjunto, recupera solo los calificadores que se almacena en el espacio de nombres inmediato. |
| `WBEM_FLAG_DEEP` | 0 | La enumeración incluye todas las subclases de la jerarquía, pero no en esta clase. |
| `WBEM_FLAG_SHALLOW` | 1 | La enumeración incluye únicamente las instancias de esta clase puras y excluye todas las instancias de subclases que proporcionan las propiedades que no se encuentran en esta clase. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca provoca una llamada semisincrónica. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La función devuelve un enumerador de solo avance. Normalmente, los enumeradores de sólo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI mantiene punteros a objetos en la enumeración hasta que se publican. |

Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para mejorar el rendimiento.

`pCtx`\
[in] Normalmente, este valor es `null`. En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instancia que se puede usar el proveedor que proporciona las clases solicitadas.

`ppEnum`\
[out] Recibe el puntero en el enumerador.

`authLevel`\
[in] El nivel de autorización.

`impLevel`\
[in] El nivel de suplantación.

`pCurrentNamespace`\
[in] Un puntero a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto que representa el espacio de nombres actual.

`strUser`\
[in] El nombre de usuario. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

`strPassword`\
[in] La contraseña. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

`strAuthority`\
[in] El nombre de dominio del usuario. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para ver una o varias de las clases que puede devolver la función. |
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strSuperClass` no existe. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI era probablemente detenido y volver a iniciar. Llame a [ConnectServerWmi](connectserverwmi.md) nuevo. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) método.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)