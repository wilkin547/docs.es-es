---
title: Recopilación de diagnósticos en contenedores
description: En este artículo, aprenderá cómo se pueden usar las herramientas de diagnóstico de .NET Core en contenedores de Docker.
ms.date: 09/01/2020
ms.openlocfilehash: cf4bbdf75e943f093a2202f91303a2eea7125487
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916214"
---
# <a name="collect-diagnostics-in-containers"></a>Recopilación de diagnósticos en contenedores

Las mismas herramientas de diagnóstico que son útiles para diagnosticar problemas de .NET Core en otros escenarios también funcionan en contenedores de Docker. Sin embargo, algunas de las herramientas requieren pasos especiales para funcionar en un contenedor. En este artículo se explica cómo se pueden usar herramientas para reunir seguimientos del rendimiento y recopilar volcados en contenedores de Docker.

## <a name="using-net-core-cli-tools-in-a-container"></a>Uso de herramientas de CLI de .NET Core en un contenedor

**Estas herramientas se aplican a: ✔️** SDK de .NET Core 3.0 y versiones posteriores

Las herramientas de diagnóstico de la CLI global de .NET Core ([`dotnet-counters`](dotnet-counters.md), [`dotnet-dump`](dotnet-dump.md), [`dotnet-gcdump`](dotnet-gcdump.md) y [`dotnet-trace`](dotnet-trace.md)) están diseñadas para funcionar en una amplia variedad de entornos y deberían funcionar directamente en contenedores de Docker. Por este motivo, estas herramientas son el método preferido para recopilar información de diagnóstico para escenarios de .NET Core que tienen como destino .NET Core 3.0 o superior (o 3.1 o superior en el caso de `dotnet-gcdump`) en contenedores.

El único factor que complica el uso de estas herramientas en un contenedor es que se instalan con el SDK de .NET Core y muchos contenedores de Docker se ejecutan sin el SDK de .NET Core presente. Una solución sencilla a este problema es instalar las herramientas en la imagen inicial de Docker. Las herramientas no necesitan que el SDK de .NET Core se ejecute, solo que esté instalado. Por lo tanto, es posible crear un Dockerfile con una [compilación de varias fases](https://docs.docker.com/develop/develop-images/multistage-build/) que instale las herramientas en una fase de compilación (donde esté presente el SDK de .NET Core) y, a continuación, copie los archivos binarios en la imagen final. El único inconveniente de este enfoque es el aumento del tamaño de la imagen de Docker.

```dockerfile
# In build stage
# Install desired .NET CLI diagnostics tools
RUN dotnet tool install --tool-path /tools dotnet-trace
RUN dotnet tool install --tool-path /tools dotnet-counters
RUN dotnet tool install --tool-path /tools dotnet-dump

...

# In final stage
# Copy diagnostics tools
WORKDIR /tools
COPY --from=build /tools .
```

Como alternativa, el SDK de .NET Core se puede instalar en un contenedor cuando sea necesario para instalar las herramientas de la CLI. Tenga en cuenta que la instalación del SDK de .NET Core tendrá como efecto secundario la reinstalación del entorno de ejecución de .NET Core. Asegúrese de instalar la versión del SDK que coincida con el entorno de ejecución presente en el contenedor.

### <a name="using-net-core-global-cli-tools-in-a-sidecar-container"></a>Uso de las herramientas de la CLI global de .NET Core en un contenedor sidecar

Si desea usar las herramientas de diagnóstico de la CLI global de .NET Core para diagnosticar los procesos en otro contenedor, tenga en cuenta los siguientes requisitos adicionales:

1. Los contenedores deben [compartir un espacio de nombres de proceso](https://docs.docker.com/engine/reference/run/#pid-settings---pid) (de modo que las herramientas del contenedor sidecar puedan acceder a los procesos del contenedor de destino).
2. Las herramientas de diagnóstico de la CLI global de .NET Core necesitan acceso a los archivos que el entorno de ejecución de .NET Core escribe en el directorio /tmp, por lo que el directorio /tmp debe compartirse entre el contenedor de destino y sidecar a través de un montaje de volumen. Esto puede hacerse, por ejemplo, haciendo que los contenedores compartan un [volumen](https://docs.docker.com/storage/volumes/#create-and-manage-volumes) común o un volumen [emptyDir](https://kubernetes.io/docs/concepts/storage/volumes/#emptydir) de Kubernetes. Si intenta usar las herramientas de diagnóstico desde un contenedor sidecar sin compartir el directorio /tmp, obtendrá un error que indica que el proceso "no está ejecutando un entorno de ejecución de .NET compatible".

## <a name="using-perfcollect-in-a-container"></a>Uso de `PerfCollect` en un contenedor

**Esta herramienta se aplica a: ✔️** .NET Core 2.1 y versiones posteriores

El script [`PerfCollect`](./trace-perfcollect-lttng.md) resulta útil para recopilar seguimientos del rendimiento y es la herramienta recomendada para recopilar seguimientos anteriores a .NET Core 3.0. Si utiliza `PerfCollect` en un contenedor, tenga en cuenta los siguientes requisitos:

1. `PerfCollect` requiere la [funcionalidad `SYS_ADMIN`](https://man7.org/linux/man-pages/man7/capabilities.7.html) (para ejecutar la herramienta `perf`), por lo que debe asegurarse de que el contenedor se [inicia con esa capacidad](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities).
2. `PerfCollect` requiere que se establezcan algunas variables de entorno antes de que se inicie la generación de perfiles de la aplicación. Se pueden establecer en un [Dockerfile](https://docs.docker.com/engine/reference/builder/#env) o cuando [se inicia el contenedor](https://docs.docker.com/engine/reference/run/#env-environment-variables). Dado que estas variables no deben establecerse en entornos de producción normales, es habitual simplemente agregarlas al iniciar un contenedor del que se va a crear un perfil. Las dos variables que requiere PerfCollect son:
    1. COMPlus_PerfMapEnabled=1
    1. COMPlus_EnableEventLog=1

### <a name="using-perfcollect-in-a-sidecar-container"></a>Uso de `PerfCollect` en un contenedor sidecar

Si desea ejecutar `PerfCollect` en un contenedor para generar perfiles de un proceso de .NET Core en un contenedor diferente, la experiencia es prácticamente la misma, con la salvedad de estas diferencias:

1. Las variables de entorno mencionadas previamente (COMPlus_PerfMapEnabled y COMPlus_EnableEventLog) se deben establecer para el contenedor de destino (no el que ejecuta `PerfCollect`).
2. El contenedor que ejecuta `PerfCollect` debe tener la funcionalidad `SYS_ADMIN` (no el contenedor de destino).
3. Los dos contenedores deben [compartir un espacio de nombres de proceso](https://docs.docker.com/engine/reference/run/#pid-settings---pid).

## <a name="using-createdump-in-a-container"></a>Uso de `createdump` en un contenedor

**Esta herramienta se aplica a: ✔️** .NET Core 2.1 y versiones posteriores

Alternativa a `dotnet-dump`, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) se puede usar para crear volcados principales en Linux que contienen información nativa y administrada. La herramienta `createdump` se instala con el entorno de ejecución de .NET y se puede encontrar junto a libcoreclr.so (normalmente en "/usr/share/dotnet/shared/Microsoft.NETCore.App/[versión]"). La herramienta funciona de la misma forma en un contenedor que en entornos de Linux no contenedores con la única excepción de que la herramienta requiere la [capacidad `SYS_PTRACE`](https://man7.org/linux/man-pages/man7/capabilities.7.html), por lo que el contenedor de Docker debe [iniciarse con esa capacidad](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities).

### <a name="using-createdump-in-a-sidecar-container"></a>Uso de `createdump` en un contenedor sidecar

Si desea usar `createdump` para crear un volcado de memoria a partir de un proceso en un contenedor diferente, la experiencia es prácticamente la misma, con la salvedad de estas diferencias:

1. El contenedor que ejecuta `createdump` debe tener la funcionalidad `SYS_PTRACE` (no el contenedor de destino).
2. Los dos contenedores deben [compartir un espacio de nombres de proceso](https://docs.docker.com/engine/reference/run/#pid-settings---pid).
