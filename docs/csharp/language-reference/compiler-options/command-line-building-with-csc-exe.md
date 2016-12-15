---
title: "Compilar la l&#237;nea de comandos con csc.exe | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
  - "CSharp"
helpviewer_keywords: 
  - "compilaciones [C#]"
  - "línea de comandos [C#]"
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilar la l&#237;nea de comandos con csc.exe
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede invocar el compilador de C# escribiendo el nombre de su archivo ejecutable (csc.exe) en un símbolo del sistema.  
  
 Si utiliza el **Visual Studio Command Prompt** ventana, todas las variables de entorno necesarias se establecen automáticamente. En Windows 7, puede tener acceso a esa ventana desde el **iniciar** menú, abra Microsoft Visual Studio *versión*carpeta de \Visual Studio Tools. En Windows 8, el símbolo del sistema de Visual Studio se denomina el **símbolo del sistema para desarrolladores de VS2012**, y puede encontrarlo buscando desde la pantalla de inicio.  
  
 Si usa una ventana de símbolo del sistema estándar, debe ajustar la ruta de acceso antes de poder invocar a csc.exe desde cualquier subdirectorio del equipo. También debe ejecutar vsvars32.bat para establecer las variables de entorno adecuadas para admitir las compilaciones desde la línea de comandos. Para obtener más información sobre vsvars32.bat, incluyendo instrucciones para buscarlo y ejecutarlo, vea [Cómo: establecer Variables de entorno para el símbolo del sistema de Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Si está trabajando en un equipo que sólo tiene el [!INCLUDE[winsdklong](../../../csharp/language-reference/compiler-options/includes/winsdklong_md.md)], puede utilizar el compilador de C# en el **SDK Command Prompt**, que puede abrir desde el **Microsoft .NET Framework SDK** opción de menú.  
  
 También puede usar MSBuild para compilar programas de C# mediante programación. Para obtener más información, consulte [MSBuild](/visual-studio/msbuild/msbuild1).  
  
 El archivo ejecutable csc.exe se encuentra normalmente en el NET\Framework\\*versión* carpeta bajo el directorio de Windows. Su ubicación puede variar, según la configuración exacta de un equipo concreto. Si se instala más de una versión de .NET Framework en el equipo, encontrará varias versiones de este archivo. Para obtener más información sobre estas instalaciones, vea [determinar qué versión del .NET Framework está instalado](http://msdn.microsoft.com/es-es/1a87cc6a-1c4b-4c38-b878-faa9b3beae3c).  
  
> [!TIP]
>  Cuando compila un proyecto mediante el IDE de Visual Studio, puede mostrar el **csc** comando y las opciones del compilador asociadas en la **salida** ventana. Para mostrar esta información, siga las instrucciones de [Cómo: ver, guardar y configurar archivos de registro de compilación](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md) para cambiar el nivel de detalle de los datos de registro para **Normal** o **detallado**. Después de volver a generar el proyecto, busque el **salida** ventana **csc** para localizar la invocación del compilador de C#.  
  
 **En este tema**  
  
-   [Reglas para la sintaxis de línea de comandos](#vcconcommand-linebuildinganchor1)  
  
-   [Líneas de comandos de ejemplo](#vcconcommand-linebuildinganchor2)  
  
-   [Diferencias entre el resultado del compilador de C++ y el compilador de C#](#vcconcommand-linebuildinganchor3)  
  
##  <a name="a-namevcconcommand-linebuildinganchor1a-rules-for-command-line-syntax-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor1"></a> Reglas para la sintaxis de línea de comandos para el compilador de C#  
 El compilador de C# utiliza las siguientes reglas para interpretar los argumentos empleados en la línea de comandos del sistema operativo:  
  
-   Los argumentos van delimitados por espacio en blanco, que puede ser un carácter de espacio o una tabulación.  
  
-   El carácter de intercalación (^) no se reconoce como carácter de escape ni como delimitador. El analizador de la línea de comandos del sistema operativo procesa este carácter antes de pasarlo a la matriz argv del programa.  
  
-   Una cadena entre comillas ("cadena") se interpreta como un solo argumento, sin importar el espacio en blanco que contenga. Se puede incrustar una cadena entre comillas dentro de un argumento.  
  
-   Unas comillas precedidas por una barra diagonal inversa (\\") se interpreta como un carácter literal de comillas dobles (").  
  
-   Las barras diagonales inversas se interpretan literalmente, a menos que precedan inmediatamente a unas comillas.  
  
-   Si a un número par de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz argv por cada par de barras diagonales y se interpretan las comillas como delimitador de cadenas.  
  
-   Si a un número impar de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz argv por cada par de barras diagonales y se interpretan las comillas como un carácter de escape gracias a la barra diagonal restante. Esto hace que se agregue un literal de comillas dobles (") a argv.  
  
##  <a name="a-namevcconcommand-linebuildinganchor2a-sample-command-lines-for-the-c-compiler"></a><a name="vcconcommand-linebuildinganchor2"></a> Líneas de comandos de ejemplo para el compilador de C#  
  
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
  
##  <a name="a-namevcconcommand-linebuildinganchor3a-differences-between-c-compiler-and-c-compiler-output"></a><a name="vcconcommand-linebuildinganchor3"></a> Diferencias entre el resultado del compilador de C++ y el compilador de C#  
 No se crean archivos objeto (.obj) como resultado de invocar el compilador de C#; se crean directamente archivos de salida. Como consecuencia de ello, el compilador de C# no requiere un vinculador.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Opciones del compilador de C# alfabético](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [Opciones del compilador de C#, por categoría](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)   
 [Cómo: Mostrar argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Cómo: argumentos de línea de comandos de acceso mediante foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)