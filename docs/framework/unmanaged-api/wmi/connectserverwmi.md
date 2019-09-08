---
title: Función ConnectServerWmi (referencia de la API no administrada)
description: La función ConnectServerWmi usa DCOM para crear una conexión a un espacio de nombres WMI.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798753"
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi función)

Crea una conexión a un espacio de nombres de WMI a través de DCOM en un equipo especificado.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a>Parámetros

`strNetworkResource`\
de Puntero a un válido `BSTR` que contiene la ruta de acceso del objeto del espacio de nombres WMI correcto. Vea la sección [comentarios](#remarks) para obtener más información.

`strUser`\
de Un puntero a un válido `BSTR` que contiene el nombre de usuario. Un `null` valor indica el contexto de seguridad actual. Si el usuario es de un dominio diferente del actual, `strUser` también puede contener el dominio y el nombre de usuario separados por una barra diagonal inversa. `strUser`también puede tener el formato de nombre principal de usuario (UPN), `userName@domainName`como. Vea la sección [comentarios](#remarks) para obtener más información.

`strPassword`\
de Un puntero a un válido `BSTR` que contiene la contraseña. `null` Indica el contexto de seguridad actual. Una cadena vacía ("") indica una contraseña de longitud cero válida.

`strLocale`\
de Un puntero a un válido `BSTR` que indica la configuración regional correcta para la recuperación de información. En el caso de los identificadores de configuración regional de Microsoft, el formato\_de la cadena es "MS*XXX*", donde *XXX* es una cadena en formato hexadecimal que indica el identificador de configuración regional (LCID). Si se especifica una configuración regional no válida, el método `WBEM_E_INVALID_PARAMETER` devuelve excepto en Windows 7, donde se usa en su lugar la configuración regional predeterminada del servidor. Si es "null1", se usa la configuración regional actual.

`lSecurityFlags`\
de Marcas que se van a `ConnectServerWmi` pasar al método. Un valor de cero (0) para este parámetro hace que `ConnectServerWmi` la llamada solo se devuelva después de establecer una conexión con el servidor. Esto podría dar lugar a que una aplicación no responda indefinidamente si el servidor está dañado. Los otros valores válidos son:

| Constante  | Value  | DESCRIPCIÓN  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Reservado para uso interno. No usar. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi`devuelve en dos minutos o menos. |

`strAuthority`\
de El nombre de dominio del usuario. Puede tener los siguientes valores:

| Valor | DESCRIPCIÓN |
|---------|---------|
| En blanco | Se usa la autenticación NTLM y se usa el dominio NTLM del usuario actual. Si `strUser` especifica el dominio (la ubicación recomendada), no debe especificarse aquí. La función devuelve `WBEM_E_INVALID_PARAMETER` si se especifica el dominio en ambos parámetros. |
| Kerberos:*nombre principal* | Se usa la autenticación Kerberos y este parámetro contiene un nombre de entidad de seguridad Kerberos. |
| NTLMDOMAIN:*nombre de dominio* | Se usa la autenticación NT LAN Manager y este parámetro contiene un nombre de dominio NTLM. |

`pCtx`\
de Normalmente, este parámetro es `null`. De lo contrario, es un puntero a un objeto [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) requerido por uno o más proveedores de clases dinámicas.

`ppNamespace`\
enuncia Cuando la función devuelve, recibe un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) enlazado al espacio de nombres especificado. Se establece de forma que apunte `null` a cuando se produce un error.

`impLevel`\
de Nivel de suplantación.

`authLevel`\
de Nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) .

Para el acceso local al espacio de nombres `strNetworkResource` predeterminado, puede ser una ruta de acceso de objeto simple:\\"root\default" o ".\root\default". Para obtener acceso al espacio de nombres predeterminado de un equipo remoto mediante com o redes compatibles con Microsoft, incluya el nombre del\\equipo: "myserver\root\default". El nombre del equipo también puede ser un nombre DNS o una dirección IP. La `ConnectServerWmi` función también se puede conectar con equipos que ejecutan IPv6 mediante una dirección IPv6.

`strUser`no puede ser una cadena vacía. Si el dominio se especifica en `strAuthority`, no se debe incluir también en `strUser`, o la función devuelve `WBEM_E_INVALID_PARAMETER`.

## <a name="requirements"></a>Requisitos

 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

 **Encabezado**: WMINet_Utils.idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
