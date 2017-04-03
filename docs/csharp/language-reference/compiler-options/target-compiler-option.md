---
title: /target (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target
dev_langs:
- CSharp
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 615a0e2993dc78919008e8f9245504a486e2fb77
ms.lasthandoff: 03/13/2017

---
# <a name="target-c-compiler-options"></a>/target (Opciones del compilador de C#)
La opción del compilador **/target** se puede especificar en uno de cuatro formatos:  
  
 [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Para crear un archivo .exe para aplicaciones de [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
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
  
 A menos que se especifique **/target:module**, **/target** hace que se coloque un manifiesto de ensamblado de .NET Framework en un archivo de salida. Para más información, vea [Ensamblados en Common Language Runtime](https://msdn.microsoft.com/library/k3677y81) y [Atributos comunes](http://msdn.microsoft.com/library/2f48a7ec-9683-4899-a1d2-a08be8fc558b).  
  
 El manifiesto de ensamblado se coloca en el primer archivo de salida .exe de la compilación o en el primer archivo DLL si no hay ningún archivo de salida .exe. Por ejemplo, en la siguiente línea de comandos, el manifiesto se colocará en `1.exe`:  
  
```  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 El compilador crea solo un manifiesto de ensamblado por compilación. La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado. Todos los archivos de salida, excepto los creados con **/target:module**, pueden contener un manifiesto de ensamblado. Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos. Independientemente de cuál sea el primer archivo de salida (**/target:exe**, **/target:winexe**, **/target:library** o **/target:module**), los demás archivos de salida generados en la misma compilación deben ser módulos (**/target:module**).  
  
 Si crea un ensamblado, puede indicar que todo o parte del código es conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.  
  
```  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Para más información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [/subsystemversion (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
