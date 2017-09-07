---
title: -win32icon (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32icon
dev_langs:
- CSharp
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
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
ms.openlocfilehash: af5b9c3a44163167d932d378cbac4976e07eacbf
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="win32icon-c-compiler-options"></a>/win32icon (Opciones del compilador de C#)
La opción **/win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia deseada en el Explorador de archivos.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El archivo .ico que quiere agregar a su archivo de salida.  
  
## <a name="remarks"></a>Comentarios  
 Se puede crear un archivo .ico con el [compilador de recursos](http://go.microsoft.com/fwlink/?LinkId=148370). Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.  
  
 Vea [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (para hacer referencia) o [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework. Vea [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) para importar un archivo .res.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra las páginas **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Icono de aplicación**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

