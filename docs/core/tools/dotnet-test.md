---
title: Comando dotnet-test | SDK de .NET Core
description: El comando &quot;dotnet test&quot; se usa para ejecutar pruebas unitarias en un proyecto determinado.
keywords: dotnet-test, CLI, comando de la CLI, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: c6ee3f5663d0a3f62914e8de474cca4d15340c9d
ms.openlocfilehash: b12861f0ce3c40bf4db51994ea5d4a92b8ef0162

---

#<a name="dotnettest"></a>dotnet-test

## <a name="name"></a>Name

`dotnet-test`-Ejecuta pruebas unitarias mediante el ejecutor de pruebas configurado.

## <a name="synopsis"></a>Sinopsis

`dotnet test [project] [--help] 
    [--parentProcessId] [--port] [--configuration]   
    [--output] [--build-base-path] [--framework] [--runtime]
    [--no-build]`  

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. Las pruebas unitarias son proyectos de biblioteca de clases que tienen dependencias en el marco de pruebas unitarias (por ejemplo, NUnit o xUnit) y en el ejecutor dotnet test de ese marco de pruebas unitarias. Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba también deben especificar una propiedad test runner en project.json mediante el nodo "testRunner". Este valor debe contener el nombre del marco de pruebas unitarias.

El archivo project.json de ejemplo siguiente muestra las propiedades necesarias:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable"
  },
  "dependencies": {
    "System.Runtime.Serialization.Primitives": "4.1.1",
    "xunit": "2.1.0",
    "dotnet-test-xunit": "1.0.0-rc2-192208-24"
  },
  "testRunner": "xunit",
  "frameworks": {
    "netcoreapp1.0": {
      "dependencies": {
        "Microsoft.NETCore.App": {
          "type": "platform",
          "version": "1.0.0"
        }
      },
      "imports": [
        "dotnet5.4",
        "portable-net451+win8"
      ]
    }
  }
}
```

`dotnet test`admite dos modos de ejecución:

1. Consola: en el modo de consola, `dotnet test` ejecuta completamente cualquier comando pasado a él y genera los resultados. Cada vez que se invoca `dotnet test` sin pasar --port, se ejecuta en modo de consola, lo que a su vez hará que el ejecutor se ejecute en modo de consola.
2. Tiempo de diseño: se usa en el contexto de otras herramientas, como editores o entornos de desarrollo integrado (IDE). Puede encontrar más información sobre este modo en el documento sobre el [protocolo dotnet-test](test-protocol.md). 

## <a name="options"></a>Opciones

`[project]`
    
Especifica una ruta de acceso al proyecto de prueba. Si se omite, se toma como predeterminado el directorio actual.

`-?|-h|--help`

Imprime una corta ayuda para el comando.

`--parentProcessId`

Se usa en los IDE para especificar su identificador de proceso. La prueba se terminará si el proceso principal también lo hace.

`--port`

Se usa en los IDE para especificar un número de puerto para escuchar una conexión.

`-c|--configuration <Debug|Release>`

Configuración con la que se va a realizar la compilación. El valor predeterminado es `Release`. 

`-o|--output [OUTPUT_DIRECTORY]`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Directorio en el que se van a colocar las salidas temporales.

`-f|--framework [FRAMEWORK]`

Busca archivos binarios de prueba para un marco específico.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Busca archivos binarios de prueba para el tiempo de ejecución especificado.

`--no-build` 

No compila el proyecto de prueba antes de ejecutarlo. 

## <a name="examples"></a>Ejemplos

Ejecución de las pruebas en el proyecto en el directorio actual:

`dotnet test` 

Ejecución de las pruebas en el proyecto test1:

`dotnet test /projects/test1/project.json` 

## <a name="see-also"></a>Vea también

[Protocolo de comunicación dotnet-test](test-protocol.md)

[Marcos](../../standard/frameworks.md)

[Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)


<!--HONumber=Nov16_HO1-->


