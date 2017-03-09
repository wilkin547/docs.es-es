---
title: "/doc (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "FileProperties.BuildAction"
  - "/doc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "comments, C# code"
  - "XML documentation [C#], comments in source files"
  - "doc compiler option [C#]"
  - "Visual C#, XML documentation for"
  - "-doc compiler option [C#]"
  - "/doc compiler option [C#]"
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# /doc (C# Compiler Options)
La opción **\/doc** permite insertar comentarios de documentación en un archivo XML.  
  
## Sintaxis  
  
```  
/doc:file  
```  
  
## Argumentos  
 `file`  
 Archivo de salida para XML, que se llena con los comentarios de los archivos del código fuente de la compilación.  
  
## Comentarios  
 En los archivos de código fuente, pueden procesarse y agregarse al archivo XML los comentarios de documentación que preceden a los citados a continuación:  
  
-   Tipos definidos por el usuario como una [clase](../../../csharp/language-reference/keywords/class.md), un [delegado](../../../csharp/language-reference/keywords/delegate.md) o una [interfaz](../../../csharp/language-reference/keywords/interface.md)  
  
-   Miembros como un campo, un [evento](../../../csharp/language-reference/keywords/event.md), una [propiedad](../../../csharp/programming-guide/classes-and-structs/using-properties.md) o un método.  
  
 El código fuente que contiene Main es el primero que se extrae al archivo XML.  
  
 Para utilizar el archivo .xml generado junto con la característica [IntelliSense](/visual-studio/ide/using-intellisense), dé el mismo nombre al archivo .xml que al ensamblado que con el desee tener compatibilidad, y asegúrese de que ambos estén en el mismo directorio.  Así, cuando se haga referencia al ensamblado en el proyecto de Visual Studio, también se encontrará el archivo .xml.  Vea [Proporcionar comentarios al código](/visual-studio/ide/supplying-xml-code-comments) para obtener más información.  
  
 A menos que se compile con [\/target: módulo](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), `file` contendrá \<el ensamblado\>\<y las etiquetas\> de ensamblado que especifique el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.  
  
> [!NOTE]
>  La opción \/doc se aplica a todos los archivos de entrada; o bien, si se ha establecido en la configuración del proyecto, a todos los archivos en el proyecto.  Para deshabilitar las advertencias relacionadas con los comentarios de documentación de un archivo o sección de código en particular, utilice [\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Vea [Etiquetas recomendadas para comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) para conocer los modos de generar documentación a partir de los comentarios del código.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la pestaña **Compilar**.  
  
3.  Modifique la propiedad **Archivo de documentación XML**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)