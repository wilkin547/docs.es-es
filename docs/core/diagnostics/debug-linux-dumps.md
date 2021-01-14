---
title: Depuración de volcados de memoria de Linux
description: En este artículo, aprenderá a recopilar y analizar volcados de memoria desde entornos de Linux.
ms.date: 08/27/2020
ms.openlocfilehash: e6f2eea3af718853ad7365a5209b397a66035dde
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753606"
---
# <a name="debug-linux-dumps"></a>Depuración de volcados de memoria de Linux

**Este artículo se aplica a: ✔️** SDK de .NET Core 3.0 y versiones posteriores

## <a name="collect-dumps-on-linux"></a>Recopilación de volcados de memoria en Linux

Las dos formas recomendadas de recopilar volcados en Linux son las siguientes:

* Herramienta de la CLI [`dotnet-dump`](dotnet-dump.md)
* [Variables de entorno](dumps.md#collecting-dumps-on-crash) que recopilan volcados de memoria al producirse bloqueos

### <a name="managed-dumps-with-dotnet-dump"></a>Volcados administrados con `dotnet-dump`

La herramienta [`dotnet-dump`](dotnet-dump.md) es fácil de usar y no depende de ningún depurador nativo. `dotnet-dump` funciona en una amplia variedad de plataformas Linux (como Alpine o ARM32/ARM64) donde las herramientas tradicionales de depuración pueden no estar disponibles. Pero `dotnet-dump` solo captura el estado administrado, por lo que no se puede usar para la depuración de problemas en código nativo. Los volcados de memoria recopilados por `dotnet-dump` se analizan en un entorno con el mismo sistema operativo y la misma arquitectura con los que se ha creado el volcado de memoria. La herramienta [`dotnet-gcdump`](dotnet-gcdump.md) se puede usar como alternativa, ya que solo captura información del montón de recolección de elementos no utilizados (GC), pero genera volcados que se puedan analizar en Windows.

### <a name="core-dumps-with-createdump"></a>Volcados de núcleo con `createdump`

Como alternativa a `dotnet-dump`, que crea volcados solo de información administrada, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) es la herramienta recomendada para crear volcados de núcleo en Linux que contienen tanto información nativa como administrada. También se pueden usar otras herramientas como gdb o gcore para crear volcados de núcleo, pero puede omitir el estado necesario para la depuración administrada, lo que puede dar lugar a nombres de función o de tipo desconocidos durante el análisis.

La herramienta `createdump` se instala con el entorno de ejecución de .NET y se puede encontrar junto a libcoreclr.so (normalmente en "/usr/share/dotnet/shared/Microsoft.NETCore.App/[versión]"). Esta herramienta toma un identificador de proceso para recopilar un volcado de su argumento principal, y también puede tomar parámetros opcionales que especifican el tipo de volcado que se va a recopilar (el valor predeterminado es un minivolcado con montón). Las opciones son:

- **`<input-filename>`**

  Archivo de seguimiento de entrada que se va a convertir. El valor predeterminado es *trace.nettrace*.

### <a name="options"></a>Opciones

- **`-f|--name <output-filename>`**

  Archivo en el que se escribirá el volcado. El valor predeterminado es "/tmp/coredump.%p", donde "%p" es el identificador del proceso de destino.

- **`-n|--normal`**

  Creación de un minivolcado.

- **`-h|--withheap`**

  Creación de un minivolcado con montón (valor predeterminado).

- **`-t|--triage`**

  Creación de un minivolcado de evaluación de prioridades.

- **`-u|--full`**

  Creación de un volcado de núcleo completo.

- **`-d|--diag`**

  Habilitación de mensajes de diagnóstico.

La recopilación de volcados de núcleo requiere la capacidad `SYS_PTRACE` o la ejecución de `createdump` con sudo o su.

## <a name="analyze-dumps-on-linux"></a>Análisis de volcados de memoria en Linux

Los volcados de memoria recopilados con `dotnet-dump` y los volcados de núcleo recopilados con `createdump` se pueden analizar con la herramienta `dotnet-dump` mediante el comando `dotnet-dump analyze`. `dotnet dump` requiere que el entorno que analiza el volcado tenga el mismo sistema operativo y la misma arquitectura que el entorno en el que se capturó el volcado.

Como alternativa, se puede usar [LLDB](https://lldb.llvm.org/) para analizar los volcados de núcleo en Linux, ya que permite el análisis de marcos administrados y nativos. LLDB usa la extensión SOS para depurar el código administrado. La herramienta de la CLI [`dotnet-sos`](dotnet-sos.md) se puede usar para instalar SOS, que tiene [muchos comandos útiles](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) para depurar código administrado. Para poder analizar los volcados de .NET Core, LLDB y SOS requieren los siguientes archivos binarios de .NET Core del entorno en el que se creó el volcado:

1. libmscordaccore.so
2. libcoreclr.so
3. dotnet (host usado para iniciar la aplicación)

En la mayoría de los casos, estos archivos binarios se pueden descargar mediante la herramienta [`dotnet-symbol`](dotnet-symbol.md). Si no se pueden descargar los archivos binarios necesarios con `dotnet-symbol` (por ejemplo, si está en uso una versión privada de .NET Core creada a partir de un origen), puede que sea necesario copiar los archivos enumerados anteriormente desde el entorno en el que se creó el volcado. Si los archivos no se encuentran junto al archivo de volcado de memoria, puede usar el comando `setclrpath <path>` de LLDB/SOS para establecer la ruta de acceso desde la que se deben cargar, y `setsymbolserver -directory <path>` para establecer la ruta de acceso de los archivos de símbolos.

Una vez que están disponibles los archivos necesarios, el volcado de memoria se puede cargar en LLDB especificando el host de dotnet como el ejecutable que se va a depurar:

```console
lldb --core <dump-file> <host-program>
```

En la línea de comandos anterior, `<dump-file>` es la ruta de acceso del volcado que se va a analizar y `<host-program>` es el programa nativo que inició la aplicación .NET Core. Este suele ser el archivo binario `dotnet`, a menos que la aplicación sea independiente, en cuyo caso es el nombre de la aplicación sin la extensión .dll.

Una vez que se inicia LLDB, puede que sea necesario usar el comando `setsymbolserver` para apuntar a la ubicación de los símbolos correcta (`setsymbolserver -ms` para usar el servidor de símbolos de Microsoft o `setsymbolserver -directory <path>` para especificar una ruta de acceso local). Los símbolos nativos se pueden cargar mediante la ejecución de `loadsymbols`. En este punto, se pueden usar [comandos SOS](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) para analizar el volcado de memoria.

## <a name="see-also"></a>Consulte también

- [dotnet-sos](dotnet-sos.md) para obtener más información sobre la instalación de la extensión SOS.
- [dotnet-symbol](dotnet-symbol.md) para obtener más información sobre la instalación y el uso de la herramienta de descarga de símbolos.
- [Repositorio de diagnósticos de .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/) para obtener más información sobre la depuración, incluidas las preguntas más frecuentes.
- [Instalación de LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) para obtener instrucciones sobre la instalación de LLDB en Linux o Mac.
