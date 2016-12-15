---
title: "/win32icon (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/win32icon"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32icon compiler option [C#]"
  - "/win32icon compiler option [C#]"
  - "-win32icon compiler option [C#]"
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /win32icon (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción de **\/win32icon** incrusta un archivo .ico en el archivo de salida, que proporciona al archivo de salida la apariencia deseada en el Explorador del archivo.  
  
## Sintaxis  
  
```  
/win32icon:filename  
```  
  
## Argumentos  
 `filename`  
 Archivo .ico que se desea agregar al archivo de salida.  
  
## Comentarios  
 Un archivo .ico se puede crear con [Compilador de recursos](http://go.microsoft.com/fwlink/?LinkId=148370).  El compilador de recursos se invoca cuando se compila un programa de Visual C\+\+; se crea un archivo .ico a partir del archivo .rc.  
  
 Vea [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) \(para hacer referencia a\) o [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) \(para asociar\) un archivo de recursos de .NET Framework.  Vea [\/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) para importar un archivo .res.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra las páginas **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique el valor de la propiedad **Icono de aplicación**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## Ejemplo  
 Para compilar `in.cs` y asociar un archivo .ico `rf.ico` con el fin de generar `in.exe`, ejecute:  
  
```  
csc /win32icon:rf.ico in.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)