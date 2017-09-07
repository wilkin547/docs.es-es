---
title: -win32res (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32res
dev_langs:
- CSharp
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4552b526767584e62106b2b10f8a1e6394a23b46
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="win32res-c-compiler-options"></a>/win32res (Opciones del compilador de C#)
La opción **/win32res** inserta un recurso de Win32 en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/win32res:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El archivo de recursos que quiere agregar a su archivo de salida.  
  
## <a name="remarks"></a>Comentarios  
 Se puede crear un archivo de recursos de Win32 con el [compilador de recursos](http://go.microsoft.com/fwlink/?LinkId=148370). Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .res a partir del archivo .rc.  
  
 Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayudaría a identificar la aplicación en el Explorador de archivos. Si no especifica **/win32res**, el compilador generará información de versión basada en la versión del ensamblado.  
  
 Vea [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (para hacer referencia) o [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Haga clic en el botón **Archivo de recursos** y seleccione un archivo mediante el cuadro combinado.  
  
## <a name="example"></a>Ejemplo  
 Compile `in.cs` y adjunte un archivo de recursos de Win32 `rf.res` para producir `in.exe`:  
  
```console  
csc /win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

