---
title: 'Volcados de memoria: .NET'
description: Una introducción a los volcados de memoria en .NET.
ms.date: 10/12/2020
ms.openlocfilehash: 56cf4085d10658c828bac39be93eed3f774e00d5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242778"
---
# <a name="dumps"></a>Volcados

Un volcado de memoria es un archivo que contiene una instantánea del proceso en el momento en que se ha creado y puede ser útil para examinar el estado de la aplicación. Los volcados de memoria se pueden usar para depurar la aplicación de .NET cuando es difícil asociarle un depurador, como los entornos de producción o de CI. El uso de volcados de memoria permite capturar el estado del proceso con problemas y examinarlo sin tener que detener la aplicación.

## <a name="collect-dumps"></a>Recopilación de volcados de memoria

Los volcados de memoria se pueden recopilar de varias maneras, en función de la plataforma en la que se ejecute la aplicación.

> [!NOTE]
> La recopilación de un volcado de memoria dentro de un contenedor requiere la funcionalidad PTRACE, que se puede agregar a través de `--cap-add=SYS_PTRACE` o `--privileged`.

> [!NOTE]
> Los volcados de memoria pueden incluir información confidencial, ya que pueden contener la memoria completa del proceso en ejecución. Para controlarlos, siga las restricciones e instrucciones de seguridad.

### <a name="collecting-dumps-on-crash"></a>Recopilación de volcados de memoria durante un bloqueo

Puede usar variables de entorno a fin de configurar la aplicación para que recopile un volcado de memoria tras un bloqueo. Esto resulta útil si quiere comprender por qué se ha producido un bloqueo. Por ejemplo, la captura de un volcado de memoria cuando se inicia una excepción le ayuda a identificar un problema mediante el examen del estado de la aplicación en el momento del bloqueo.

En la tabla siguiente se muestran las variables de entorno que se pueden configurar para la recopilación de volcados de memoria en caso de bloqueo.

|Variable de entorno|Descripción|Valor predeterminado|
|-------|---------|---|
|`COMPlus_DbgEnableMiniDump`|Si se establece en 1, se habilita la generación de volcado de memoria principal.|0|
|`COMPlus_DbgMiniDumpType`|Tipo de volcado de memoria que se va a recopilar. Para obtener más información, vea la tabla siguiente.|2 (`MiniDumpWithPrivateReadWriteMemory`)|
|`COMPlus_DbgMiniDumpName`|Ruta de acceso a un archivo en el que se escribirá el volcado de memoria.|`/tmp/coredump.<pid>`|
|`COMPlus_CreateDumpDiagnostics`|Si se establece en 1, se habilita el registro de diagnóstico del proceso de volcado.|0|

En la tabla siguiente se muestran todas las opciones que puede usar para `COMPlus_DbgMiniDumpType` que se pueden especificar como un valor. Por ejemplo, si `COMPlus_DbgMiniDumpType` se establece en 1, significa que el volcado de tipo `MiniDumpNormal` se recopilará al producirse un bloqueo.

|Value|Nombre|Descripción|
|-----|----|-----------|
|1|`MiniDumpNormal`|Incluya solo la información necesaria para capturar seguimientos de pila para todos los subprocesos existentes en un proceso. Información y memoria del montón de GC limitadas.|
|2|`MiniDumpWithPrivateReadWriteMemory`|Incluye la información y los montones de GC necesarios para capturar seguimientos de pila para todos los subprocesos existentes en un proceso.|
|3|`MiniDumpFilterTriage`|Incluya solo la información necesaria para capturar seguimientos de pila para todos los subprocesos existentes en un proceso. Información y memoria del montón de GC limitadas.|
|4|`MiniDumpWithFullMemory`|Incluya toda la memoria accesible en el proceso. Los datos de memoria sin procesar se incluyen al final, de modo que las estructuras iniciales se pueden asignar directamente sin la información de memoria sin procesar. Esta opción puede dar lugar a un archivo muy grande.|

### <a name="collecting-dumps-at-specific-point-in-time"></a>Recopilación de volcados de memoria en un momento dado

Es posible que quiera recopilar un volcado de memoria cuando la aplicación todavía no se ha bloqueado. Por ejemplo, si quiere examinar el estado de una aplicación que parece estar en un interbloqueo, la configuración de las variables de entorno para recopilar volcados de memoria al producirse un bloqueo no será útil porque la aplicación todavía está en ejecución.

Para recopilar el volcado de memoria cuando prefiera, puede usar `dotnet-dump`, que es una herramienta de la CLI para la recopilación y el análisis de volcados de memoria. Para obtener más información sobre cómo usarla para recopilar volcados de memoria con `dotnet-dump`, vea [Utilidad de recopilación y análisis de volcados de memoria](dotnet-dump.md).

## <a name="analyze-dumps"></a>Análisis de volcados de memoria

Los volcados de memoria se pueden analizar mediante [`dotnet-dump`](dotnet-dump.md).

## <a name="see-also"></a>Consulte también

Obtenga más información sobre cómo puede aprovechar los volcados de memoria para ayudar a diagnosticar problemas en la aplicación de .NET.

* En el tutorial [Depuración de volcados de Linux](debug-linux-dumps.md) se le guía a través de la depuración de un volcado de memoria recopilado en Linux.

* En el tutorial [Depuración de interbloqueo](debug-deadlock.md) se le guía a través de la depuración de un interbloqueo en la aplicación de .NET mediante volcados de memoria.
