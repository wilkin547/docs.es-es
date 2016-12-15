---
title: "/moduleassemblyname (C# Compiler Option) | Microsoft Docs"
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
  - "/moduleassemblyname"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "moduleassemblyname compiler option [C#]"
  - "/moduleassemblyname compiler option [C#]"
  - ".moduleassemblyname compiler option [C#]"
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /moduleassemblyname (C# Compiler Option)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica un ensamblado a cuyos tipos no públicos puede tener acceso un .netmodule.  
  
## Sintaxis  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## Argumentos  
 `assembly_name`  
 El nombre del ensamblado cuyos tipos privados el .netmodule tiene acceso.  
  
## Comentarios  
 **\/moduleassemblyname** debe utilizar al compilar un .netmodule, y donde se cumplen las condiciones siguientes:  
  
-   El .netmodule necesita acceso a los tipos privados de un ensamblado existente.  
  
-   Conoce el nombre del ensamblado donde el .netmodule se compilará.  
  
-   El ensamblado existente ha concedido acceso al ensamblado de confianza al ensamblado donde el .netmodule se compilará.  
  
 Para obtener más información sobre cómo compilar un .netmodule, vea [\/target:module \(Create Module to Add to Assembly\)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Para obtener más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Esta opción no está disponible en el entorno de desarrollo; sólo está disponible al compilar desde la línea de comandos.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## Ejemplo  
 Este ejemplo compila un ensamblado con un tipo privado que concede acceso de ensamblado de confianza a un ensamblado llamado csman\_an\_assembly.  
  
```  
// moduleassemblyname_1.cs  
// compile with: /target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## Ejemplo  
 Este ejemplo compila un .netmodule que tiene acceso a un tipo privado del ensamblado moduleassemblyname\_1.dll.  Sabiendo que este .netmodule se compilará en un ensamblado denominado csman\_an\_assembly, se puede especificar **\/moduleassemblyname**, permitiendo que el .netmodule tener acceso a los tipos privados de un ensamblado que ha concedido el acceso del ensamblado de confianza a csman\_an\_assembly.  
  
```  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## Ejemplo  
 Este ejemplo de código compila el ensamblado csman\_an\_assembly, haciendo referencia al ensamblado y el .netmodule anterior\- compilados.  
  
```  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
  **Se llama a An\_Internal\_Class.Test**   
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)