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
# <a name="configure-a-proxy-server-when-using-the-azure-sdk-for-net"></a><span data-ttu-id="f049a-103">Configuración de un servidor proxy al usar Azure SDK para .NET</span><span class="sxs-lookup"><span data-stu-id="f049a-103">Configure a proxy server when using the Azure SDK for .NET</span></span>

<span data-ttu-id="f049a-104">Si su organización requiere el uso de un servidor proxy para acceder a recursos de Internet, deberá establecer una variable de entorno con la información del servidor proxy para usar Azure SDK para .NET.</span><span class="sxs-lookup"><span data-stu-id="f049a-104">If your organization requires the use of a proxy server to access internet resources, you will need to set an environment variable with the proxy server information to use the Azure SDK for .NET.</span></span>  

## <a name="configuration-using-environment-variables"></a><span data-ttu-id="f049a-105">Configuración mediante variables de entorno</span><span class="sxs-lookup"><span data-stu-id="f049a-105">Configuration using environment variables</span></span>

<span data-ttu-id="f049a-106">Dependiendo de si el servidor proxy usa HTTP o HTTPS, deberá establecer las variables de entorno `HTTP_PROXY` o `HTTPS_PROXY` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f049a-106">Depending on if your proxy server uses HTTP or HTTPS, you will set either the environment variable `HTTP_PROXY` or `HTTPS_PROXY` respectively.</span></span> <span data-ttu-id="f049a-107">La dirección URL del servidor proxy tiene el formato `http[s]://[username:password@]<ip_address_or_hostname>:<port>/`, donde la combinación `username:password` es opcional.</span><span class="sxs-lookup"><span data-stu-id="f049a-107">The proxy server URL has the form `http[s]://[username:password@]<ip_address_or_hostname>:<port>/` where the `username:password` combination is optional.</span></span> <span data-ttu-id="f049a-108">Para obtener la dirección IP o el nombre del host, el puerto y las credenciales del servidor proxy, consulte al administrador de la red.</span><span class="sxs-lookup"><span data-stu-id="f049a-108">To get the IP address or hostname, port and credentials for your proxy server, consult your network administrator.</span></span>

<span data-ttu-id="f049a-109">En los siguientes ejemplos se muestra cómo establecer las variables de entorno adecuadas en entornos de shell de comandos (Windows) y de Bash (Linux o Mac).</span><span class="sxs-lookup"><span data-stu-id="f049a-109">The following examples show how to set the appropriate environment variables in command shell (Windows) and bash (Linux/Mac) environments.</span></span>  <span data-ttu-id="f049a-110">La configuración de la variable de entorno adecuada hará que Azure SDK para .NET use el servidor proxy en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f049a-110">Setting the appropriate environment variable will then cause the Azure SDK for .NET to use the proxy server at runtime.</span></span>

### <a name="cmd"></a>[<span data-ttu-id="f049a-111">cmd</span><span class="sxs-lookup"><span data-stu-id="f049a-111">cmd</span></span>](#tab/cmd)

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

### <a name="bash"></a>[<span data-ttu-id="f049a-112">bash</span><span class="sxs-lookup"><span data-stu-id="f049a-112">bash</span></span>](#tab/bash)

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
