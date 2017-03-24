---
title: "Valores devueltos de Main() (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Main (método) [C#], valores devueltos"
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Valores devueltos de Main() (Gu&#237;a de programaci&#243;n de C#)
El método `Main` puede devolver `void`:  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]  
  
 También puede devolver un valor de tipo `int`:  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]  
  
 Si no se usa el valor devuelto por el método `Main`, la devolución de `void` permite un código un poco más simple.  Sin embargo, la devolución de un entero permite que el programa comunique información de estado a otros programas o scripts que invocan el archivo ejecutable.  En el ejemplo siguiente, se muestra cómo se puede obtener acceso al valor devuelto de `Main`.  
  
## Ejemplo  
 En este ejemplo, se usa un archivo por lotes para ejecutar un programa y probar el valor devuelto de la función `Main`.  Cuando un programa se ejecuta en Windows, cualquier valor que devuelva la función `Main` se almacena en una variable de entorno denominada `ERRORLEVEL`.  Al inspeccionar la variable `ERRORLEVEL`, los archivos por lotes pueden determinar el resultado de la ejecución.  Tradicionalmente, un valor devuelto de cero indica una ejecución correcta.  El siguiente ejemplo es un programa sencillo que devuelve el valor cero para la función `Main`.  El cero indica que el programa se ejecutó correctamente.  Guarde el programa como MainReturnValTest.cs.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]  
  
## Ejemplo  
 Dado que en este ejemplo se usa un archivo por lotes, se recomienda compilar el código desde un símbolo del sistema.  Siga las instrucciones que se describen en [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) para habilitar las compilaciones desde la línea de comandos, o bien, use el símbolo del sistema de Visual Studio, que está disponible en el menú **Inicio** bajo **Visual Studio Tools**.  Desde el símbolo del sistema, navegue hasta la carpeta donde guardó el programa.  El comando siguiente compila MainReturnValTest.cs y genera el archivo ejecutable MainReturnValTest.exe.  
  
 `csc MainReturnValTest.cs`  
  
 A continuación, cree un archivo por lotes para ejecutar MainReturnValTest.exe y mostrar el resultado.  Pegue el código siguiente en un archivo de texto y guárdelo como `test.bat` en la carpeta que contiene MainReturnValTest.cs y MainReturnValTest.exe.  Ejecute el archivo por lotes; para ello, escriba `test` en el símbolo del sistema.  
  
 Dado que el código devuelve el valor cero, el archivo por lotes se ejecutará correctamente.  Sin embargo, si cambia MainReturnValTest.cs de modo que se devuelva un valor distinto de cero y, a continuación, vuelve a compilar el programa, la ejecución subsiguiente del archivo por lotes generará un error.  
  
```  
rem test.bat  
@echo off  
MainReturnValTest  
@if "%ERRORLEVEL%" == "0" goto good  
  
:fail  
    echo Execution Failed  
    echo return value = %ERRORLEVEL%  
    goto end  
  
:good  
    echo Execution succeeded  
    echo Return value = %ERRORLEVEL%  
    goto end  
  
:end  
```  
  
## Resultados del ejemplo  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Main\(\) y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)