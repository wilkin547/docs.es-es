---
title: -target:winmdobj (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f690591b79159a0196a1637903f2cc53442976e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="targetwinmdobj-c-compiler-options"></a>/target:winmdobj (Opciones del compilador de C#)
Si usa la opción del compilador **/target:winmdobj**, el compilador crea un archivo .winmdobj intermedio que puede convertir en un archivo binario de Windows Runtime (.winmd). A continuación, pueden usar el archivo .winmd programas de JavaScript y C++, además de los programas de lenguajes administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/target:winmdobj  
```  
  
## <a name="remarks"></a>Comentarios  
 El valor **winmdobj** indica al compilador que un módulo intermedio es obligatorio. En respuesta, Visual Studio compila la biblioteca de clases de C# como archivo .winmdobj. El archivo .winmdobj se puede alimentar entonces a través de la herramienta de exportación <xref:Microsoft.Build.Tasks.WinMDExp> para producir un archivo de metadatos de Windows (.winmd). El archivo .winmd contiene el código de la biblioteca original y los metadatos de WinMD que usan JavaScript o C++ y Windows en tiempo de ejecución.  
  
 La salida de un archivo compilado mediante la opción del compilador **/target:winmdobj** solo sirve para usarse como entrada de la herramienta de exportación WimMDExp; no se hace referencia directa al propio archivo .winmdobj.  
  
 A menos que use la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el nombre del archivo de salida adopta el nombre del primer archivo de entrada. No se requiere un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Si especifica la opción /target:winmdobj en un símbolo del sistema, todos los archivos hasta la siguiente opción **/out** o [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) se usan para crear el programa de Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Para establecer esta opción del compilador en el IDE de Visual Studio para una aplicación de la Tienda Windows  
  
1.  En el **Explorador de soluciones**, abra el menú contextual del proyecto y, después, pulse **Propiedades**.  
  
2.  Pulse la pestaña **Aplicación**.  
  
3.  En la lista **Tipo de resultado**, pulse **Archivo WinMD**.  
  
     La opción **Archivo WinMD** solo está disponible para las plantillas de aplicación de [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila `filename.cs` en un archivo .winmdobj intermedio.  
  
```console  
csc /target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [/target (opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
