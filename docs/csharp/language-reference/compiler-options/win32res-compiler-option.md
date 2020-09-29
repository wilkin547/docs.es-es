---
description: -win32res (Opciones del compilador de C#)
title: -win32res (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 442c788595a01db9c0a1196d9e13b2a98963a38c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204351"
---
# <a name="-win32res-c-compiler-options"></a>-win32res (Opciones del compilador de C#)

La opción **-win32res** inserta un recurso de Win32 en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a>Argumentos  

 `filename`  
 El archivo de recursos que quiere agregar a su archivo de salida.  
  
## <a name="remarks"></a>Comentarios  

 Se puede crear un archivo de recursos de Win32 con el [compilador de recursos](resource-compiler-option.md). Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .res a partir del archivo .rc.  
  
 Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayudaría a identificar la aplicación en el Explorador de archivos. Si no especifica **-win32res**, el compilador generará información de versión basada en la versión del ensamblado.  
  
 Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades **Aplicación**.  
  
3. Haga clic en el botón **Archivo de recursos** y seleccione un archivo mediante el cuadro combinado.  
  
## <a name="example"></a>Ejemplo  

 Compile `in.cs` y adjunte un archivo de recursos de Win32 `rf.res` para producir `in.exe`:  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
