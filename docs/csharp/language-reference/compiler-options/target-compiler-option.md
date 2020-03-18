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
ms.openlocfilehash: af7bd917f57c8752a2026fbb98aa8b22adc98db7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74204516"
---
# <a name="-target-c-compiler-options"></a>-target (Opciones del compilador de C#)
La opción del compilador **-target** se puede especificar en uno de estos cuatro formatos:  
  
 [/target:appcontainerexe](./target-appcontainerexe-compiler-option.md)  
 Para crear un archivo .exe para aplicaciones de la Tienda Windows 8.x.  
  
 [/target:exe](./target-exe-compiler-option.md)  
 Para crear un archivo .exe.  
  
 [/target:library](./target-library-compiler-option.md)  
 Para crear una biblioteca de código.  
  
 [/target:module](./target-module-compiler-option.md)  
 Para crear un módulo.  
  
 [/target:winexe](./target-winexe-compiler-option.md)  
 Para crear un programa de Windows.  
  
 [/target:winmdobj](./target-winmdobj-compiler-option.md)  
 Para crear un archivo .winmdobj intermedio.  
  
 A menos que se especifique **-target:module**, **-target** hace que se coloque un manifiesto de ensamblado de .NET Framework en un archivo de salida. Para obtener más información, vea [Ensamblados en .NET](../../../standard/assembly/index.md) y [Atributos comunes](../../programming-guide/concepts/attributes/common-attributes.md).  
  
 El manifiesto de ensamblado se coloca en el primer archivo de salida .exe de la compilación o en el primer archivo DLL si no hay ningún archivo de salida .exe. Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 El compilador crea solo un manifiesto de ensamblado por compilación. La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado. Todos los archivos de salida, excepto los creados con **-target:module**, pueden contener un manifiesto de ensamblado. Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos. Independientemente de cuál sea el primer archivo de salida ( **-target:exe**, **-target:winexe**, **-target:library** o **-target:module**), los demás archivos de salida generados en la misma compilación deben ser módulos ( **-target:module**).  
  
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

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
- [-subsystemversion (Opciones del compilador de C#)](./subsystemversion-compiler-option.md)
