---
title: Compilar la línea de comandos con csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: f692e66672b1804a309c6ac04c158af948a1b1ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789869"
---
# <a name="command-line-build-with-cscexe"></a>Compilar la línea de comandos con csc.exe

Puede invocar el compilador de C# escribiendo el nombre de su archivo ejecutable (*csc.exe*) en un símbolo del sistema.

Si usa la ventana **Símbolo del sistema para desarrolladores de Visual Studio**, todas las variables de entorno necesarias se establecen automáticamente. Para obtener información sobre cómo acceder a esta herramienta, vea el tema [Símbolo del sistema para desarrolladores de Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

Si usa una ventana de símbolo del sistema estándar, debe ajustar la ruta de acceso antes de poder invocar *csc.exe* desde cualquier subdirectorio del equipo. También debe ejecutar *vsvars32.bat* para establecer las variables de entorno adecuadas para admitir las compilaciones desde la línea de comandos. Para obtener más información sobre *vsvars32.bat*, incluidas las instrucciones sobre cómo buscarlo y ejecutarlo, vea [Procedimiento para establecer variables de entorno para la línea de comandos de Visual Studio](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).

Si trabaja en un equipo que solo tiene el kit de desarrollo de software (SDK) de Windows, puede usar el compilador de C# en el **símbolo del sistema de SDK**, que puede abrir desde la opción de menú **Microsoft .NET Framework SDK**.

También puede usar MSBuild para compilar programas de C# mediante programación. Para obtener más información, vea [MSBuild](/visualstudio/msbuild/msbuild).

El archivo ejecutable *csc.exe* suele encontrarse en la carpeta Microsoft.NET\Framework\\*\<Versión>* del directorio de *Windows*. Su ubicación puede variar, según la configuración exacta de un equipo concreto. Si se instala más de una versión de .NET Framework en el equipo, encontrará varias versiones de este archivo. Para obtener más información sobre estas instalaciones, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).

> [!TIP]
> Al compilar un proyecto mediante el IDE de Visual Studio, puede mostrar el comando **csc** y las opciones del compilador asociadas en la ventana **Salida**. Para mostrar esta información, siga las instrucciones de [Cómo: Ver, guardar y configurar archivos de registro de compilación](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) para cambiar el nivel de detalle de los datos del registro a **Normal** o **Detallado**. Una vez recompilado el proyecto, busque **csc** en la ventana **Salida** para localizar la invocación del compilador de C#.

 **En este tema**

- [Reglas para la sintaxis de la línea de comandos](#rules-for-command-line-syntax-for-the-c-compiler)

- [Líneas de comandos de ejemplo](#sample-command-lines-for-the-c-compiler)

- [Diferencias entre el resultado del compilador de C++ y el compilador de C#](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a>Reglas para la sintaxis de la línea de comandos para el compilador de C#

El compilador de C# utiliza las siguientes reglas para interpretar los argumentos empleados en la línea de comandos del sistema operativo:

- Los argumentos van delimitados por espacio en blanco, que puede ser un carácter de espacio o una tabulación.

- El carácter de intercalación (^) no se reconoce como carácter de escape ni como delimitador. El analizador de la línea de comandos del sistema operativo procesa este carácter antes de pasarlo a la matriz `argv` del programa.

- Una cadena entre comillas ("cadena") se interpreta como un solo argumento, sin importar el espacio en blanco que contenga. Se puede incrustar una cadena entre comillas dentro de un argumento.

- Unas comillas precedidas por una barra diagonal inversa (\\") se interpretan como un literal de cadena de comillas (").

- Las barras diagonales inversas se interpretan literalmente, a menos que precedan inmediatamente a unas comillas.

- Si a un número par de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz `argv` por cada par de barras diagonales y se interpretan las comillas como delimitador de cadenas.

- Si a un número impar de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz `argv` por cada par de barras diagonales y se interpretan las comillas como un carácter de "escape" gracias a la barra diagonal restante. Esto hace que se agregue un literal de comillas dobles (") a `argv`.

## <a name="sample-command-lines-for-the-c-compiler"></a>Líneas de comandos de ejemplo para el compilador de C#

- Compila *File.cs* y genera *File.exe*:

  ```console
  csc File.cs
  ```

- Compila *File.cs* y genera *File.dll*:

  ```console
  csc -target:library File.cs
  ```

- Compila *File.cs* y crea *My.exe*:

  ```console
  csc -out:My.exe File.cs
  ```

- Compila todos los archivos de C# del directorio actual, con optimizaciones habilitadas y define el símbolo DEBUG. El resultado es *File2.exe*:

  ```console
  csc -define:DEBUG -optimize -out:File2.exe *.cs
  ```

- Compila todos los archivos de C# del directorio actual, generando una versión de depuración de *File2.dll*. No se muestra logotipo ni ningún tipo de advertencias:

  ```console
  csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
  ```

- Compila todos los archivos de C# del directorio actual en *Something.xyz* (un DLL):

  ```console
  csc -target:library -out:Something.xyz *.cs
  ```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a>Diferencias entre el resultado del compilador de C++ y el compilador de C#

No se crean archivos objeto (*.obj*) como resultado de invocar el compilador de C#; se crean directamente archivos de salida. Como consecuencia de ello, el compilador de C# no requiere un vinculador.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Opciones del compilador de C#, por orden alfabético](./listed-alphabetically.md)
- [Opciones del compilador de C#, por categoría](./listed-by-category.md)
- [Main() y argumentos de la línea de comandos](../../programming-guide/main-and-command-args/index.md)
- [Argumentos de la línea de comandos](../../programming-guide/main-and-command-args/command-line-arguments.md)
- [Procedimiento Mostrar argumentos de la línea de comandos](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [Valores devueltos de Main()](../../programming-guide/main-and-command-args/main-return-values.md)
