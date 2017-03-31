---
title: "Valores devueltos de Main() (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
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
ms.openlocfilehash: 846c52b7d5429a23f354dd6a732ddb62563a55bf
ms.lasthandoff: 03/13/2017

---
# <a name="main-return-values-c-programming-guide"></a>Valores devueltos de Main() (Guía de programación de C#)
El método `Main` puede devolver el valor `void`:  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]  
  
 También puede devolver un valor `int`:  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]  
  
 Si el valor devuelto de `Main` no se usa, la devolución de `void` permite contar con un código ligeramente más simple. En cambio, devolver un valor entero permite que el programa comunique información de estado a otros programas o scripts que invocan el archivo ejecutable. En el ejemplo siguiente se muestra cómo se puede acceder al valor devuelto de `Main`.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se usa un archivo por lotes para ejecutar un programa y probar el valor devuelto de la función `Main`. Cuando un programa se ejecuta en Windows, cualquier valor devuelto por la función `Main` se almacena en una variable de entorno denominada `ERRORLEVEL`. Un archivo por lotes puede determinar el resultado de la ejecución inspeccionando la variable `ERRORLEVEL`. Tradicionalmente, un valor devuelto de cero indica una ejecución correcta. El ejemplo siguiente es un programa sencillo que devuelve el valor cero de la función `Main`. El cero indica que el programa se ha ejecutado correctamente. Guarde el programa como MainReturnValTest.cs.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 Puesto que este ejemplo usa un archivo por lotes, es mejor compilar el código desde un símbolo del sistema. Siga las instrucciones de [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio) para habilitar las compilaciones de líneas de comandos o use el símbolo del sistema de Visual Studio, disponible en el menú **Inicio**, en **Visual Studio Tools**. Desde el símbolo del sistema, vaya hasta la carpeta en la que ha guardado el programa. El comando siguiente compila MainReturnValTest.cs y genera el archivo ejecutable MainReturnValTest.exe.  
  
 `csc MainReturnValTest.cs`  
  
 Luego, cree un archivo por lotes para ejecutar MainReturnValTest.exe y mostrar el resultado. Pegue el código siguiente en un archivo de texto y guárdelo como `test.bat` en la carpeta que contiene MainReturnValTest.cs y MainReturnValTest.exe. Ejecute el archivo por lotes escribiendo `test` en el símbolo del sistema.  
  
 Dado que el código devuelve el valor cero, el archivo por lotes comunicará un resultado satisfactorio. En cambio, si cambia MainReturnValTest.cs para que devuelva un valor distinto de cero y luego vuelve a compilar el programa, la ejecución posterior del archivo por lotes informará de que se ha producido un error.  
  
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
  
## <a name="sample-output"></a>Resultados del ejemplo  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md)  (Main() y argumentos de la línea de comandos)  
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
