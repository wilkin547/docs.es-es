---
title: "/main (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/main"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-main compiler option [C#]"
  - "main compiler option [C#]"
  - "/main compiler option [C#]"
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# /main (C# Compiler Options)
Esta opción especifica la clase que contiene el punto de entrada al programa, si más de una clase contiene un método **Main**.  
  
## Sintaxis  
  
```  
/main:class  
```  
  
## Argumentos  
 `class`  
 Tipo que contiene el método **Main**.  
  
## Comentarios  
 Si la compilación incluye más de un tipo con un método [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md), se puede especificar el tipo que contiene el método **Main** que se desea utilizar como punto de entrada en el programa.  
  
 Esta opción sólo se puede usar al compilar archivos .exe.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique el valor de la propiedad **Objeto de inicio**.  
  
     Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## Ejemplo  
 Para compilar `t2.cs` y `t3.cs`, y especificar que el método **Main** está en `Test2`, ejecute:  
  
```  
csc t2.cs t3.cs /main:Test2  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)