---
title: "/target:winmdobj (Opciones del compilador de C#) | Microsoft Docs"
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
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target:winmdobj (Opciones del compilador de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Si utiliza la opción de compilador **\/target:winmdobj**, el compilador crea un archivo .winmdobj intermedio que se puede convertir en un archivo binario de Windows en tiempo de ejecución \(.winmd\).  A continuación, pueden usar el archivo .winmd programas de JavaScript y C\+\+, además de los programas de lenguajes administrados.  
  
## Sintaxis  
  
```  
/target:winmdobj  
```  
  
## Comentarios  
 El valor **winmdobj** indica al compilador que un módulo intermedio es obligatorio.  En respuesta, Visual Studio compila la biblioteca de clases de C\# como archivo .winmdobj.  El archivo .winmdobj se puede alimentar entonces a través de la herramienta de exportación <xref:Microsoft.Build.Tasks.WinMDExp> para producir un archivo de metadatos de Windows \(.winmd\).  El archivo .winmd contiene el código de la biblioteca original y los metadatos de WinMD que usan JavaScript o C\+\+ y Windows en tiempo de ejecución.  
  
 La salida de un archivo compilado mediante la opción del compilador **\/target:winmdobj** solo sirve para usarse como entrada de la herramienta de exportación WimMDExp; no se hace referencia directa al propio archivo .winmdobj.  
  
 A menos que use la opción [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida adopta el nombre del primer archivo de entrada.  No se requiere un método [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md).  
  
 Si especifica la opción \/target:winmdobj en un símbolo del sistema, todos los archivos hasta la siguiente opción **\/out** o [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) se usan para crear el programa de Windows.  
  
### Para establecer esta opción del compilador en el IDE de Visual Studio para una aplicación de la Tienda Windows  
  
1.  En el **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **Propiedades**.  
  
2.  Elija la pestaña **Aplicación**.  
  
3.  En la lista **Tipo de resultado**, elija **Archivo WinMD**.  
  
     La opción **Archivo WinMD** solo está disponible para las plantillas de aplicación de la [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Ejemplo  
 El comando siguiente compila `filename.cs` en un archivo .winmdobj intermedio.  
  
```  
csc /target:winmdobj filename.cs  
```  
  
## Vea también  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)