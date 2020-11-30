---
description: -pathmap (opciones del compilador de C#)
title: -pathmap (opciones del compilador de C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 707a37c6946cfcaf429552f0aeece6b87f3ad71d
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125012"
---
# <a name="-pathmap-c-compiler-options"></a>-pathmap (opciones del compilador de C#)

La opción **-pathmap** del compilador especifica cómo asignar rutas físicas a los nombres de rutas de acceso de origen generados por el compilador.

## <a name="syntax"></a>Sintaxis

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a>Argumentos

 `path1` La ruta de acceso completa a los archivos de origen en el entorno actual

 `sourcePath1` La ruta de acceso de origen sustituida por `path1` en cualquier archivo de salida

Para especificar varias rutas de acceso de origen asignadas, sepárelas con una coma.

## <a name="remarks"></a>Comentarios

El compilador escribe la ruta de acceso de origen en la salida por las razones siguientes:

1. La ruta de acceso de origen se sustituye por un argumento cuando se aplica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parámetro opcional.
1. La ruta de acceso de origen se inserta en un archivo PDB.
1. La ruta de acceso del archivo PDB se inserta en un archivo PE (ejecutable portable).

Esta opción asigna cada ruta de acceso física en la máquina donde el compilador se ejecuta a una ruta de acceso correspondiente que debe escribirse en los archivos de salida.

## <a name="example"></a>Ejemplo

Compile `t.cs` en el directorio **C:\\work\\test** y asigne ese directorio a **\publish** en la salida:

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
