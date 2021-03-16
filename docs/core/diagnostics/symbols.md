---
title: Símbolos en .NET
description: Introducción a los símbolos y los archivos PDB portables en .NET
ms.date: 02/08/2021
ms.openlocfilehash: da59a07166cd1f73160da8d9ac53b5823bf13e7b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108415"
---
# <a name="symbols"></a>Símbolos

Los símbolos son útiles para la depuración y otras herramientas de diagnóstico. El contenido de los archivos de símbolos varia según los lenguajes, los compiladores y las plataformas. En un nivel muy alto, los símbolos son una asignación entre el código de origen y el binario que produce el compilador. Estas asignaciones las usan herramientas como [Visual Studio](/visualstudio/debugger/what-is-debugging) y [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) para resolver la información de números de línea de origen o los nombres de variables locales.

La [documentación de Windows sobre símbolos](/windows/win32/dxtecharts/debugging-with-symbols) contiene información más detallada sobre los símbolos de Windows, aunque muchos de los conceptos también se aplican a otras plataformas.

## <a name="learn-about-nets-portable-pdb-format"></a>Más información sobre el formato PDB portable de .NET

.NET Core presenta un nuevo formato de archivo de símbolos (PDB): el archivo PDB portable. A diferencia de los PDB tradicionales, que son solo para Windows, los archivos PDB portables se pueden crear y leer en todas las plataformas.

### <a name="what-is-a-pdb"></a>¿Qué es un PDB?

Un archivo PDB es un archivo auxiliar generado por un compilador para proporcionar a otras herramientas, especialmente a los depuradores, información sobre el contenido del archivo ejecutable principal y sobre cómo se ha generado. Por ejemplo, un depurador lee un archivo PDB para asignar la línea 12 de foo.cs a la ubicación ejecutable correcta para que pueda establecer un punto de interrupción. El formato PDB de Windows se ha usado durante mucho tiempo y ha evolucionado desde otros formatos de símbolos de depuración nativos que son incluso más antiguos. Comenzó como un formato para programas (C/C++) nativos. En la primera versión de .NET Framework, el formato PDB de Windows se amplió para admitir .NET.

## <a name="use-the-correct-pdb-format-for-your-scenario"></a>Uso del formato PDB correcto para su escenario

Los archivos PDB portables y los archivos PDB de Windows no se admiten en todos los casos, por lo que debe tener en cuenta dónde deseará usar y depurar el proyecto para decidir qué formato debe usar. Si tiene un proyecto que desea poder usar y depurar en ambos formatos, puede usar diferentes configuraciones de compilación y compilar el proyecto dos veces para admitir ambos tipos de consumidores.

### <a name="support-for-portable-pdbs"></a>Compatibilidad con archivos PDB portables

Los archivos PDB portables se pueden leer en cualquier sistema operativo y es el formato de símbolos recomendado para el código administrado, pero hay una serie de herramientas y aplicaciones heredadas en las que no se admiten:

* Aplicaciones para .NET Framework 4.7.1 o versiones anteriores: los seguimientos de la pila de impresión con asignaciones a los números de línea (por ejemplo, en una página de error de ASP.NET). El nombre de los métodos no se ve afectado, solo no se admiten los nombres de archivo de origen y los números de línea.

* Usar descompiladores de .NET como Ildasm o .NET reflector y esperar ver las asignaciones de líneas de origen o los nombres de parámetros locales.

* Las versiones más recientes de [DIA](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk) y las herramientas que lo usan para leer símbolos, como WinDBG, admiten archivos PDB portables, pero la versión anterior no.

* Puede haber versiones anteriores de los perfiles que no admitan los archivos PDB portables.

Para usar PDB portables en herramientas que no los admiten, puede probar a usar Pdb2Pdb[https://github.com/dotnet/symreader-converter#pdb2pdb ], que realiza una conversión entre archivos PDB portables y archivos PDB de Windows.

### <a name="support-for-windows-pdbs"></a>Compatibilidad con archivos PDB de Windows

Los archivos PDB de Windows solo se pueden escribir o leer en Windows. El uso de archivos PDB de Windows para código administrado está obsoleto y solo es necesario para las herramientas heredadas. Se recomienda usar archivos PDB portables en lugar de archivos PDB de Windows ya que algunas características de compilador más recientes se han implementado solo para archivos PDB portables.

## <a name="see-also"></a>Vea también

* [dotnet-symbol](./dotnet-symbol.md) se puede usar para descargar archivos de símbolos para elementos binarios de marco

* [Documentación de Windows sobre símbolos](/windows/win32/dxtecharts/debugging-with-symbols)
