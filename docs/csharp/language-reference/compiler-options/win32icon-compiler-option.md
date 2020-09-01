---
description: -win32icon (Opciones del compilador de C#)
title: -win32icon (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 76a54f9011371492bdc15f15c3e40d51082deed3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138415"
---
# <a name="-win32icon-c-compiler-options"></a>-win32icon (Opciones del compilador de C#)
La opción **-win32icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia esperada en el Explorador de archivos.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El archivo .ico que quiere agregar a su archivo de salida.  
  
## <a name="remarks"></a>Observaciones  
 Se puede crear un archivo .ico con el [compilador de recursos](/windows/desktop/menurc/resource-compiler). Cuando se compila un programa de Visual C++, se invoca el compilador de recursos y se crea un archivo .ico a partir del archivo .rc.  
  
 Vea [-linkresource](./linkresource-compiler-option.md) (para hacer referencia) o [-resource](./resource-compiler-option.md) (para adjuntar) un archivo de recursos de .NET Framework. Vea [-win32res](./win32res-compiler-option.md) para importar un archivo .res.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra las páginas **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades **Aplicación**.  
  
3. Modifique la propiedad **Icono de aplicación**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `in.cs` y adjunte un archivo .ico `rf.ico` para producir `in.exe`:  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
