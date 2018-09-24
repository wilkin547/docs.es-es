---
title: -target:winexe (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: f77137e3cc2f734435d3b1d391a303fcd3e16332
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45970180"
---
# <a name="-targetwinexe-c-compiler-options"></a>-target:winexe (Opciones del compilador de C#)
La opción **-target:winexe** hace que el compilador cree un programa de Windows ejecutable (EXE).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Comentarios  
 El archivo ejecutable se creará con la extensión .exe. Un programa de Windows es aquel que ofrece una interfaz de usuario de la biblioteca de .NET Framework o con las API Win32.  
  
 Use [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) para crear una aplicación de consola.  
  
 A menos que se especifique de otro modo con la opción [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) para crear el programa de Windows.  
  
 Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe. La opción [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Tipo de salida**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `in.cs` en un programa de Windows:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>Vea también  

- [-target (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
