---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: d8f9c9aac87fd71b61a5413386582ae660efd903
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593074"
---
# <a name="-win32resource"></a>-win32resource
Inserta un archivo de recursos de Win32 en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre del archivo de recursos para agregar al archivo de salida. Ponga el nombre de archivo entre comillas ("") si contiene un espacio.  
  
## <a name="remarks"></a>Comentarios  
 Puede crear un archivo de recursos de Win32 con el compilador de recursos de Microsoft Windows (RC).  
  
 Un recurso de Win32 puede contener la versión o información de mapa de bits (icono) que ayuda a identificar la aplicación en **Explorador de archivos**. Si no especifica `-win32resource`, el compilador genera información de versión basada en la versión del ensamblado. El `-win32resource` y `-win32icon` opciones son mutuamente excluyentes.  
  
 Consulte [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un archivo de recursos de .NET Framework.  
  
> [!NOTE]
>  El `-win32resource` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y adjunta un archivo de recursos de Win32, `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
