---
title: Función ConnectServerWmi (referencia de API no administrada)
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
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416142"
---
# <a name="connectserverwmi-function"></a>Función ConnectServerWmi
Crea una conexión a través de DCOM para un espacio de nombres WMI en un equipo especificado.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
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

`strNetworkResource` [in] Puntero a una `BSTR` que contiene la ruta de acceso del espacio de nombres WMI correcto. Consulte la [comentarios](#remarks) sección para obtener más información.

`strUser` [in] Un puntero a una `BSTR` que contiene el nombre de usuario. Un `null` valor indica el contexto de seguridad actual. Si el usuario es de un dominio diferente que el actual, `strUser` también puede contener el nombre de usuario y dominio separado por una barra diagonal inversa. `strUser` También puede ser de usuario (UPN) del nombre principal dar formato, suhc como *userName@domainName*. Consulte la [comentarios](#remarks) sección para obtener más información.

`strPassword` [in] Un puntero a una `BSTR` que contiene la contraseña. Un `null` indica el contexto de seguridad actual. Una cadena vacía ("") indica que una contraseña válida de longitud cero.

`strLocale` [in] Un puntero a una `BSTR` que indica la configuración regional correcta para la recuperación de información. Para los identificadores de configuración regional de Microsoft, el formato de la cadena es "MS\_*xxx*", donde *xxx* es una cadena en formato hexadecimal que indica el identificador de configuración regional (LCID). Si se especifica una configuración regional no válido, el método devuelve `WBEM_E_INVALID_PARAMETER` excepto en Windows 7, donde la configuración regional predeterminada del servidor se usa en su lugar. Si ' se usa null1, la configuración regional actual. 
 
`lSecurityFlags` [in] Marcas para pasar a la `ConnectServerWmi` método. Da como resultado un valor de cero (0) para este parámetro en la llamada a `ConnectServerWmi` devolver solo una vez establecida una conexión al servidor. Esto podría dar lugar a una aplicación no responde indefinidamente si el servidor se interrumpe. Los otros valores válidos son:

| Constante  | Valor  | Descripción  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Reservado para uso interno. No utilizar. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi` se devuelve en dos minutos o menos. |

`strAuthority` [in] El nombre de dominio del usuario. Puede tener los siguientes valores:

| Valor | Descripción |
|---------|---------|
| En blanco | Se usa la autenticación NTLM y se utiliza el dominio NTLM del usuario actual. Si `strUser` especifica el dominio (la ubicación recomendada), no debe especificarse aquí. La función devuelve `WBEM_E_INVALID_PARAMETER` si especifica el dominio en los dos parámetros. |
| Kerberos:*nombre principal* | Se utiliza la autenticación Kerberos, y este parámetro contiene un nombre principal de Kerberos. |
| NTLMDOMAIN:*nombre de dominio* | Se utiliza la autenticación NT LAN Manager y este parámetro contiene un nombre de dominio NTLM. |

`pCtx`   
[in] Normalmente, este parámetro es `null`. En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) objeto requerido por uno o varios proveedores de la clase dinámica. 

`ppNamespace`  
[out] Devuelve la función recibe un puntero a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto enlazado al espacio de nombres especificado. Se establece para que apunte a `null` cuando se produce un error.

`impLevel`  
[in] El nivel de suplantación.

`authLevel`  
[in] El nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemLocator:: ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) método.

 Para el acceso local al espacio de nombres predeterminado, `strNetworkResource` puede ser una ruta de acceso de objeto simple: "root\default" o "\\.\root\default". Para el acceso al espacio de nombres predeterminado en un equipo remoto mediante redes de COM o compatible con Microsoft, incluya el nombre del equipo: "\\myserver\root\default". El nombre del equipo también puede ser un nombre DNS o dirección IP. El `ConnectServerWmi` función también puede conectar con equipos que ejecutan IPv6 mediante una dirección IPv6.

`strUser` no puede ser una cadena vacía. Si se especifica el dominio en `strAuthority`, no también debe incluirse en `strUser`, o la función devuelve `WBEM_E_INVALID_PARAMETER`.


## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
