---
title: "/win32res (C# Compiler Options) | Microsoft Docs"
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
  - "/win32res"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32res compiler option"
  - "/win32res compiler option [C#]"
  - "-win32res compiler option [C#]"
  - "win32res compiler option [C#]"
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /win32res (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/win32res**inserta un recurso Win32 en el archivo de salida.  
  
## Sintaxis  
  
```  
/win32res:filename  
```  
  
## Argumentos  
 `filename`  
 Archivo de recursos que se desea agregar al archivo de salida.  
  
## Comentarios  
 Un archivo de recursos Win32 se puede crear con [Compilador de recursos](http://go.microsoft.com/fwlink/?LinkId=148370).  Cuando se compila un programa de Visual C\+\+, se invoca el compilador de recursos y se crea un archivo .res a partir del archivo .rc.  
  
 Un recurso de Win32 puede contener información de la versión o mapas de bits \(icono\) que ayudaría a identificar la aplicación en el Explorador del archivo.  Si no se especifica la opción **\/win32res**, el compilador generará información de versión basada en la versión del ensamblado.  
  
 Vea [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) \(para hacer referencia a\) o [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) \(para asociar\) un archivo de recursos de .NET Framework.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Haga clic en el botón **Archivo de recursos** y elija un archivo mediante el cuadro combinado.  
  
## Ejemplo  
 Para compilar `in.cs` y asociar un archivo de recursos Win32 `rf.res` con el fin de generar `in.exe`, ejecute:  
  
```  
csc /win32res:rf.res in.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)