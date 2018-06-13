---
title: -target:library (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 39f6ad5839f7ca12b023502a3fc1ccde52e70899
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215354"
---
# <a name="-targetlibrary-c-compiler-options"></a>-target:library (Opciones del compilador de C#)
La opción **-target:library** hace que el compilador cree una biblioteca de vínculos dinámicos (DLL) en lugar de un archivo ejecutable (EXE).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a>Comentarios  
 El archivo DLL se creará con la extensión .dll.  
  
 A menos que se especifique lo contrario con la opción [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida adopta el nombre del primer archivo de entrada.  
  
 Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o **-target:module** para crear el archivo .dll.  
  
 Al compilar un archivo .dll, no es necesario un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Tipo de salida**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compilación de `in.cs` y creación de `in.dll`:  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [-target (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
