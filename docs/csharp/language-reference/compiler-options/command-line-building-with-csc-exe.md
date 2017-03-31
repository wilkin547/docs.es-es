---
title: "Compilar la línea de comandos con csc.exe | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aa6dd9801a141ec430bc291302fe74c35057f117
ms.lasthandoff: 03/13/2017

---
# <a name="command-line-building-with-cscexe"></a>Compilar la línea de comandos con csc.exe
Puede invocar el compilador de C# escribiendo el nombre de su archivo ejecutable (csc.exe) en un símbolo del sistema.  
  
 Si usa la ventana **Símbolo del sistema de Visual Studio**, todas las variables de entorno necesarias se establecen automáticamente. En Windows 7, puede obtener acceso a esa ventana desde el menú **Inicio**; para ello, abra la carpeta *Versión*\Visual Studio Tools de Microsoft Visual Studio. En Windows 8, el símbolo del sistema de Visual Studio se denomina **Símbolo del sistema para desarrolladores de VS2012**; lo encontrará en la pantalla Inicio.  
  
 Si usa una ventana de símbolo del sistema estándar, debe ajustar la ruta de acceso antes de poder invocar a csc.exe desde cualquier subdirectorio del equipo. También debe ejecutar vsvars32.bat para establecer las variables de entorno adecuadas para admitir las compilaciones desde la línea de comandos. Para obtener más información sobre vsvars32.bat, incluidas las instrucciones sobre cómo buscarlo y ejecutarlo, vea [Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Si trabaja en un equipo que solo tiene [!INCLUDE[winsdklong](../../../csharp/language-reference/compiler-options/includes/winsdklong_md.md)], puede usar el compilador de C# en el **símbolo del sistema de SDK**, que puede abrir desde la opción de menú **Microsoft .NET Framework SDK**.  
  
 También puede usar MSBuild para compilar programas de C# mediante programación. Para obtener más información, vea [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild1).  
  
 El archivo ejecutable csc.exe suele encontrarse en la carpeta Microsoft.NET\Framework\\*Versión* del directorio de Windows. Su ubicación puede variar, según la configuración exacta de un equipo concreto. Si se instala más de una versión de .NET Framework en el equipo, encontrará varias versiones de este archivo. Para obtener más información sobre estas instalaciones, vea [Determinar qué versión de .NET Framework está instalada](http://msdn.microsoft.com/en-us/1a87cc6a-1c4b-4c38-b878-faa9b3beae3c).  
  
> [!TIP]
>  Al compilar un proyecto mediante el IDE de Visual Studio, puede mostrar el comando **csc** y las opciones del compilador asociadas en la ventana **Salida**. Para mostrar esta información, siga las instrucciones de [Cómo: Ver, guardar y configurar archivos de registro de compilación](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7) para cambiar el nivel de detalle de los datos del registro a **Normal** o **Detallado**. Una vez recompilado el proyecto, busque **csc** en la ventana **Salida** para localizar la invocación del compilador de C#.  
  
 **En este tema**  
  
-   [Reglas para la sintaxis de la línea de comandos](#vcconcommand-linebuildinganchor1)  
  
-   [Líneas de comandos de ejemplo](#vcconcommand-linebuildinganchor2)  
  
-   [Diferencias entre el resultado del compilador de C++ y el compilador de C#](#vcconcommand-linebuildinganchor3)  
  
##  <a name="vcconcommand-linebuildinganchor1"></a> Reglas para la sintaxis de línea de comandos para el compilador de C#  
 El compilador de C# utiliza las siguientes reglas para interpretar los argumentos empleados en la línea de comandos del sistema operativo:  
  
-   Los argumentos van delimitados por espacio en blanco, que puede ser un carácter de espacio o una tabulación.  
  
-   El carácter de intercalación (^) no se reconoce como carácter de escape ni como delimitador. El analizador de la línea de comandos del sistema operativo procesa este carácter antes de pasarlo a la matriz argv del programa.  
  
-   Una cadena entre comillas ("cadena") se interpreta como un solo argumento, sin importar el espacio en blanco que contenga. Se puede incrustar una cadena entre comillas dentro de un argumento.  
  
-   Unas comillas precedidas por una barra diagonal inversa (\\") se interpretan como un literal de cadena de comillas (").  
  
-   Las barras diagonales inversas se interpretan literalmente, a menos que precedan inmediatamente a unas comillas.  
  
-   Si a un número par de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz argv por cada par de barras diagonales y se interpretan las comillas como delimitador de cadenas.  
  
-   Si a un número impar de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz argv por cada par de barras diagonales y se interpretan las comillas como un carácter de escape gracias a la barra diagonal restante. Esto hace que se agregue un literal de comillas dobles (") a argv.  
  
##  <a name="vcconcommand-linebuildinganchor2"></a> Líneas de comandos de ejemplo para el compilador de C#  
  
-   Compila File.cs y genera File.exe:  
  
    ```  
    csc File.cs   
    ```  
  
-   Compila File.cs y genera File.dll:  
  
    ```  
    csc /target:library File.cs  
    ```  
  
-   Compila File.cs y crea My.exe:  
  
    ```  
    csc /out:My.exe File.cs  
    ```  
  
-   Compila todos los archivos de C# del directorio actual, con optimizaciones activadas, y define el símbolo DEBUG. Como resultado se genera el archivo File2.exe:  
  
    ```  
    csc /define:DEBUG /optimize /out:File2.exe *.cs  
    ```  
  
-   Compila todos los archivos de C# del directorio actual, generando una versión de depuración de File2.dll. No se muestra logotipo ni ningún tipo de advertencias:  
  
    ```  
    csc /target:library /out:File2.dll /warn:0 /nologo /debug *.cs  
    ```  
  
-   Compila todos los archivos de C# del directorio actual, generando Something.xyz (una DLL):  
  
    ```  
    csc /target:library /out:Something.xyz *.cs  
    ```  
  
##  <a name="vcconcommand-linebuildinganchor3"></a> Diferencias entre los resultados del compilador de C# y el compilador de C++  
 No se crean archivos objeto (.obj) como resultado de invocar el compilador de C#; se crean directamente archivos de salida. Como consecuencia de ello, el compilador de C# no requiere un vinculador.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [C# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  (Opciones del compilador de C#, por orden alfabético)  
 [C# Compiler Options Listed by Category](../../../csharp/language-reference/compiler-options/listed-by-category.md)  (Opciones del compilador de C#, por categoría)  
 [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)   
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
