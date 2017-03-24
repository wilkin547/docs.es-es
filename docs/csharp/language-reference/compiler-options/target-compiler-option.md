---
title: "/target (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#]"
  - "/target compiler options [C#]"
  - "assemblies [C#], compiling"
  - "-target compiler options [C#]"
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# /target (C# Compiler Options)
La opción del compilador **\/target** se puede especificar de cuatro formas distintas:  
  
 [\/target: appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Para crear un archivo .exe para las aplicaciones de [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] .  
  
 [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Para crear un archivo .exe.  
  
 [\/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Para crear una biblioteca de código.  
  
 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Para crear un módulo.  
  
 [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Para crear un programa de Windows.  
  
 [\/target: winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Para crear un archivo intermedia .winmdobj.  
  
 A menos que se especifique **\/target:module**, **\/target** incluye un manifiesto del ensamblado de .NET Framework en un archivo de salida.  Para obtener más información, vea [Ensamblados en Common Language Runtime](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md) y [Atributos comunes](../Topic/Common%20Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 El manifiesto del ensamblado se sitúa en el primer archivo de salida .exe de la compilación o bien en el primer archivo DLL si no hubiera .exe.  Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:  
  
```  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 El compilador sólo crea un manifiesto del ensamblado por compilación.  En el manifiesto del ensamblado se incluye información sobre todos los archivos que intervienen en una compilación.  Todos los archivos de salida, excepto los creados con **\/target:module**, pueden contener un manifiesto del ensamblado.  Cuando se producen varios archivos de salida en la línea de comandos, sólo puede crearse un manifiesto del ensamblado y éste debe ir al primer archivo de salida especificado en la línea de comandos.  Independientemente de cuál sea el primer archivo de salida \(**\/target:exe**, **\/target:winexe**, **\/target:library** o **\/target:module**\), cualquier otro archivo de salida creado en la misma compilación debe ser un módulo \(**\/target:module**\).  
  
 Si crea un ensamblado, puede indicar que todo o parte del código sea conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.  
  
```  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Para obtener más información sobre cómo establecer mediante programación esta opción del compilador, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [\/subsystemversion \(Specify minimum subsystem version\)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)