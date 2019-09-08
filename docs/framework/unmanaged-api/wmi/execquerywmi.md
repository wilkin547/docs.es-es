---
title: Función ExecQueryWmi (referencia de la API no administrada)
description: La función ExecQueryWmi ejecuta una consulta para recuperar objetos.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8547d306819e85b838f1160d9912dd43e42f2f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798687"
---
# <a name="execquerywmi-function"></a>Función ExecQueryWmi

Ejecuta una consulta para recuperar objetos.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ExecQueryWmi (
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
de Texto de la consulta. Este parámetro no puede `null`ser.

`lFlags`\
de Combinación de marcas que afectan al comportamiento de esta función. Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

| Constante | Value  | DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Si se establece, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual. <br/> Si no se establece, la función solo recupera los calificadores almacenados en el espacio de nombres inmediato. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | La marca produce una llamada semisincrónica. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La función devuelve un enumerador de solo avance. Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI conserva los punteros a objetos en la enumeración hasta que se liberan. |
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | Garantiza que los objetos devueltos tienen suficiente información en ellos, de modo que las propiedades del sistema, como **__PATH**, **__RELPATH**y `null` **__SERVER**, no lo son. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Esta marca se utiliza para la prototipo. No ejecuta la consulta y, en su lugar, devuelve un objeto que es similar a un objeto de resultado típico. |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | Provoca el acceso directo al proveedor para la clase especificada, sin tener en cuenta su clase primaria o cualquier subclase. |

Las marcas recomendadas `WBEM_FLAG_RETURN_IMMEDIATELY` son `WBEM_FLAG_FORWARD_ONLY` y para obtener el mejor rendimiento.

`pCtx`\
de Normalmente, este valor es `null`. De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.

`ppEnum`\
enuncia Si no se produce ningún error, recibe el puntero al enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta. La consulta puede tener un conjunto de resultados con cero instancias. Vea la sección [comentarios](#remarks) para obtener más información.

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

|Constante  |Value  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | El usuario no tiene permiso para ver una o varias de las clases que la función puede devolver. |
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | La consulta tenía un error de sintaxis. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | No se admite el lenguaje de consulta solicitado. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La consulta es demasiado compleja. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | Es posible que WMI se haya detenido y reiniciado. Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La consulta especifica una clase que no existe. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) .

Esta función procesa la consulta especificada en el `strQuery` parámetro y crea un enumerador a través del que el llamador puede tener acceso a los resultados de la consulta. El enumerador es un puntero a una interfaz [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) ; los resultados de la consulta son instancias de objetos de clase que se ponen a disposición a través de la interfaz [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

Hay límites en el número de `AND` palabras clave y `OR` que se pueden usar en las consultas WQL. Un gran número de palabras clave WQL usadas en una consulta compleja puede hacer que WMI `WBEM_E_QUOTA_VIOLATION` devuelva el código de error (o `HRESULT` 0x8004106c) como un valor. El límite de palabras clave de WQL depende de la complejidad de la consulta.

Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: WMINet_Utils.idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
