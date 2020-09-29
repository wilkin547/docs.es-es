---
description: -target:exe (Opciones del compilador de C#)
title: -target:exe (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: ae1706f1ecdd396e24711070d19420faa6d34761
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193768"
---
# <a name="-targetexe-c-compiler-options"></a>-target:exe (Opciones del compilador de C#)

La opción **-target:winexe** hace que el compilador cree una aplicación de consola ejecutable (EXE).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a>Observaciones  

 La opción **-target:exe** está en vigor de manera predeterminada. El archivo ejecutable se creará con la extensión .exe.  
  
 Use [-target:winexe](./target-winexe-compiler-option.md) para crear un archivo ejecutable de un programa de Windows.  
  
 A menos que se especifique de otro modo con la opción [-out](./out-compiler-option.md), el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../programming-guide/main-and-command-args/index.md).  
  
 Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o **-target:module** para crear el archivo .exe.  
  
 Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe. La opción del compilador [-main](./main-compiler-option.md) le permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades **Aplicación**.  
  
3. Modifique la propiedad **Tipo de salida**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  

 Cada una de las siguientes líneas de comandos compilará `in.cs` y creará `in.exe`:  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [-target (Opciones del compilador de C#)](./target-compiler-option.md)
- [Opciones del compilador de C#](./index.md)
