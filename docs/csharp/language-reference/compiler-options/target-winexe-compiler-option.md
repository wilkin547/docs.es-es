---
title: -target:winexe (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target:winexe
dev_langs:
- CSharp
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
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
ms.openlocfilehash: e9a640c0cfa1d0494457f8ffe94bf15877b24919
ms.lasthandoff: 03/13/2017

---
# <a name="targetwinexe-c-compiler-options"></a>/target:winexe (Opciones del compilador de C#)
La opción **/target:winexe** hace que el compilador cree un programa de Windows ejecutable (EXE).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/target:winexe  
```  
  
## <a name="remarks"></a>Comentarios  
 El archivo ejecutable se creará con la extensión .exe. Un programa de Windows es aquel que ofrece una interfaz de usuario de la biblioteca de .NET Framework o con las API Win32.  
  
 Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) para crear una aplicación de consola.  
  
 A menos que se especifique con la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **/out** o [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) para crear el programa de Windows.  
  
 Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe. La opción [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Tipo de salida**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `in.cs` en un programa de Windows:  
  
```  
csc /target:winexe in.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  (/target [Opciones del compilador de C#])  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
