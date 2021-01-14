---
title: Configuración de un servidor proxy al usar Azure SDK para .NET
description: Use variables de entorno HTTP[S]_PROXY con el fin de definir un proxy para Azure SDK para .NET.
ms.date: 12/10/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.openlocfilehash: 64d525f8a6c277a5ac383dfded828f2fd3cfd744
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701015"
---
# <a name="configure-a-proxy-server-when-using-the-azure-sdk-for-net"></a>Configuración de un servidor proxy al usar Azure SDK para .NET

Si su organización requiere el uso de un servidor proxy para acceder a recursos de Internet, deberá establecer una variable de entorno con la información del servidor proxy para usar Azure SDK para .NET.  

## <a name="configuration-using-environment-variables"></a>Configuración mediante variables de entorno

Dependiendo de si el servidor proxy usa HTTP o HTTPS, deberá establecer las variables de entorno `HTTP_PROXY` o `HTTPS_PROXY` respectivamente. La dirección URL del servidor proxy tiene el formato `http[s]://[username:password@]<ip_address_or_hostname>:<port>/`, donde la combinación `username:password` es opcional. Para obtener la dirección IP o el nombre del host, el puerto y las credenciales del servidor proxy, consulte al administrador de la red.

En los siguientes ejemplos se muestra cómo establecer las variables de entorno adecuadas en entornos de shell de comandos (Windows) y de Bash (Linux o Mac).  La configuración de la variable de entorno adecuada hará que Azure SDK para .NET use el servidor proxy en tiempo de ejecución.

### <a name="cmd"></a>[cmd](#tab/cmd)

```cmd
rem Non-authenticated HTTP server:
set HTTP_PROXY=http://10.10.1.10:1180

rem Authenticated HTTP server:
set HTTP_PROXY=http://username:password@10.10.1.10:1180

rem Non-authenticated HTTPS server:
set HTTPS_PROXY=http://10.10.1.10:1180

rem Authenticated HTTPS server:
set HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

### <a name="bash"></a>[bash](#tab/bash)

```bash
# Non-authenticated HTTP server:
HTTP_PROXY=http://10.10.1.10:1180

# Authenticated HTTP server:
HTTP_PROXY=http://username:password@10.10.1.10:1180

# Non-authenticated HTTPS server:
HTTPS_PROXY=http://10.10.1.10:1180

# Authenticated HTTPS server:
HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

---
