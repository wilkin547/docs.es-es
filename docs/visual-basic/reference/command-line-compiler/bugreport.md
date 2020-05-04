---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793544"
---
# <a name="-bugreport"></a>-bugreport

Crea un archivo que se puede usar al archivar un informe de errores.

## <a name="syntax"></a>Sintaxis

```console
-bugreport:file
```

## <a name="arguments"></a>Argumentos

|Término|Definición|
|---|---|
|`file`|Obligatorio. Nombre del archivo que contendrá el informe de errores. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").|

## <a name="remarks"></a>Comentarios

La información siguiente se agrega a `file`:

- Una copia de todos los archivos de código fuente de la compilación.

- Una lista de las opciones del compilador que se usan en la compilación.

- Información de versión sobre el compilador, el tiempo de ejecución y el sistema operativo.

- Resultados del compilador, si los hay.

- Una descripción del problema, que se le pedirá.

- Una descripción de cómo cree que se debe corregir el problema, que se le pedirá.

Como en `file` se incluye una copia de todos los archivos de código fuente, es posible que quiera reproducir el defecto en el código (sospechoso) en el programa más corto posible.

> [!IMPORTANT]
> La opción `-bugreport` genera un archivo que contiene información potencialmente confidencial. Esto incluye la hora actual, la versión del compilador, de .NET Framework y del sistema operativo, el nombre de usuario, los argumentos de línea de comandos con los que se ha ejecutado el compilador, todo el código fuente y el formato binario de cualquier ensamblado al que se hace referencia. Se puede acceder a esta opción si se especifican las opciones de línea de comandos en el archivo Web.config para una compilación del lado servidor de una aplicación ASP.NET. Para evitarlo, modifique el archivo Machine.config para evitar que los usuarios compilen en el servidor.

Si esta opción se usa con `-errorreport:prompt`, `-errorreport:queue` o `-errorreport:send`, y la aplicación encuentra un error interno del compilador, la información de `file` se envía a Microsoft Corporation. Esa información ayudará a los ingenieros de Microsoft a identificar la causa del error y se puede usar mejorar la próxima versión de Visual Basic. De forma predeterminada, no se envía información a Microsoft. Pero al compilar una aplicación mediante `-errorreport:queue`, que está habilitada de forma predeterminada, la aplicación recopila sus informes de errores. Después, cuando el administrador del equipo inicia sesión, el sistema de informes de errores muestra una ventana emergente que permite al administrador reenviar a Microsoft los informes de errores que se hayan producido desde el inicio de sesión.

> [!NOTE]
> La opción `-bugreport` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se compila *T2.vb* y toda la información sobre los informes de errores se coloca en el archivo *Problem.txt*.

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-debug (Visual Basic)](debug.md)
- [-errorreport](errorreport.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Elemento trustLevel para securityPolicy (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
