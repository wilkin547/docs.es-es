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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649879"
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
  
 Un recurso de Win32 puede contener la versión o información de mapa de bits (icono) que le ayuda a identificar la aplicación en **Explorador de archivos**. Si no se especifica `-win32resource`, el compilador genera información de versión según la versión del ensamblado. El `-win32resource` y `-win32icon` opciones son mutuamente excluyentes.  
  
 Vea [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos, o [-recurso (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos.  
  
> [!NOTE]
>  El `-win32resource` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y adjunta un archivo de recursos de Win32, `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
