---
title: Función ExecNotificationQueryWmi (referencia de la API no administrada)
description: La función ExecNotificationQueryWmi ejecuta una consulta para recibir eventos.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3d8a7683eef52a5e91bf7aa84d5aa7db7dbdac8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130450"
---
# <a name="execnotificationquerywmi-function"></a>Función ExecNotificationQueryWmi

Ejecuta una consulta para recibir eventos. La llamada se devuelve inmediatamente y el autor de la llamada puede sondear el enumerador devuelto para los eventos a medida que llegan. Al liberar el enumerador devuelto se cancela la consulta.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

`strQueryLanguage`\
de Cadena con el lenguaje de consulta válido compatible con la administración de Windows. Debe ser "WQL", el acrónimo de lenguaje de consulta de WMI.

`strQuery`\
de Texto de la consulta. Este parámetro no se puede `null`.

`lFlags`\
de Combinación de las dos marcas siguientes que afectan al comportamiento de esta función. Estos valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.

| Constante | Valor  | Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca produce una llamada semisincrónica. Si no se establece esta marca, se produce un error en la llamada. Esto se debe a que los eventos se reciben continuamente, lo que significa que el usuario debe sondear el enumerador devuelto. El bloqueo de esta llamada indefinidamente hace que sea imposible. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La función devuelve un enumerador de solo avance. Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md). |

`pCtx`\
de Normalmente, este valor es `null`. De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona los eventos solicitados.

`ppEnum`\
enuncia Si no se produce ningún error, recibe el puntero al enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta. Vea la sección [comentarios](#remarks) para obtener más información.

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

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para ver una o varias de las clases que la función puede devolver. |
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La consulta especifica una clase que no existe. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | Se ha solicitado demasiada precisión en la entrega de eventos. Se debe especificar una tolerancia de sondeo mayor. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | La consulta solicita más información de la que puede proporcionar la administración de Windows. Este `HRESULT` se devuelve cuando una consulta de evento produce una solicitud para sondear todos los objetos de un espacio de nombres. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | La consulta tenía un error de sintaxis. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | No se admite el lenguaje de consulta solicitado. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La consulta es demasiado compleja. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Es posible que WMI se haya detenido y reiniciado. Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | No se puede analizar la consulta. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) .

Una vez que la función devuelve, el llamador pasa periódicamente el objeto `ppEnum` devuelto a la función [siguiente](next.md) para ver si hay algún evento disponible.

Hay límites en el número de palabras clave `AND` y `OR` que se pueden usar en las consultas WQL. Un gran número de palabras clave WQL usadas en una consulta compleja puede hacer que WMI devuelva el código de error `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) como un valor `HRESULT`. El límite de palabras clave de WQL depende de la complejidad de la consulta.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
