---
title: /target:winmdobj (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7581ec18db0d2741452b47ad6200482b63c102be
ms.lasthandoff: 03/13/2017

---
# <a name="targetwinmdobj-c-compiler-options"></a>/target:winmdobj (Opciones del compilador de C#)
Si usa la opción del compilador **/target:winmdobj**, el compilador crea un archivo .winmdobj intermedio que puede convertir en un archivo binario de Windows Runtime (.winmd). A continuación, pueden usar el archivo .winmd programas de JavaScript y C++, además de los programas de lenguajes administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/target:winmdobj  
```  
  
## <a name="remarks"></a>Comentarios  
 El valor **winmdobj** indica al compilador que un módulo intermedio es obligatorio. En respuesta, Visual Studio compila la biblioteca de clases de C# como archivo .winmdobj. El archivo .winmdobj se puede alimentar entonces a través de la herramienta de exportación <xref:Microsoft.Build.Tasks.WinMDExp> para producir un archivo de metadatos de Windows (.winmd). El archivo .winmd contiene el código de la biblioteca original y los metadatos de WinMD que usan JavaScript o C++ y Windows en tiempo de ejecución.  
  
 La salida de un archivo compilado mediante la opción del compilador **/target:winmdobj** solo sirve para usarse como entrada de la herramienta de exportación WimMDExp; no se hace referencia directa al propio archivo .winmdobj.  
  
 A menos que use la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el nombre del archivo de salida adopta el nombre del primer archivo de entrada. No se requiere un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Si especifica la opción /target:winmdobj en un símbolo del sistema, todos los archivos hasta la siguiente opción **/out** o [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) se usan para crear el programa de Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Para establecer esta opción del compilador en el IDE de Visual Studio para una aplicación de la Tienda Windows  
  
1.  En el **Explorador de soluciones**, abra el menú contextual del proyecto y, después, pulse **Propiedades**.  
  
2.  Pulse la pestaña **Aplicación**.  
  
3.  En la lista **Tipo de resultado**, pulse **Archivo WinMD**.  
  
     La opción **Archivo WinMD** solo está disponible para las plantillas de aplicación de [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila `filename.cs` en un archivo .winmdobj intermedio.  
  
```  
csc /target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [/target (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
