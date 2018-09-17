---
title: -target (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: a337ecbc614ff40eda42fc5263dbb52aa92b905f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668150"
---
# <a name="-target-c-compiler-options"></a>-target (Opciones del compilador de C#)
La opción del compilador **-target** se puede especificar en uno de estos cuatro formatos:  
  
 [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Para crear un archivo .exe para aplicaciones de [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Para crear un archivo .exe.  
  
 [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Para crear una biblioteca de código.  
  
 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Para crear un módulo.  
  
 [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Para crear un programa de Windows.  
  
 [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Para crear un archivo .winmdobj intermedio.  
  
 A menos que se especifique **-target:module**, **-target** hace que se coloque un manifiesto de ensamblado de .NET Framework en un archivo de salida. Para más información, vea [Ensamblados en Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) y [Atributos comunes](../../programming-guide/concepts/attributes/common-attributes.md).  
  
 El manifiesto de ensamblado se coloca en el primer archivo de salida .exe de la compilación o en el primer archivo DLL si no hay ningún archivo de salida .exe. Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 El compilador crea solo un manifiesto de ensamblado por compilación. La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado. Todos los archivos de salida, excepto los creados con **-target:module**, pueden contener un manifiesto de ensamblado. Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos. Independientemente de cuál sea el primer archivo de salida (**-target:exe**, **-target:winexe**, **-target:library** o **-target:module**), los demás archivos de salida generados en la misma compilación deben ser módulos (**-target:module**).  
  
 Si crea un ensamblado, puede indicar que todo o parte del código es conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Para obtener más información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>Vea también  

- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
- [-subsystemversion (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
