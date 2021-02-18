---
description: Mas información sobre -win32resource
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
ms.openlocfilehash: a6f14fd2eb1349940c1e208a5baaa4205647f666
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433489"
---
# <a name="-win32resource"></a>-win32resource

Inserta un archivo recursos de Win32 en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumentos  

 `filename`  
 Nombre del archivo de recursos que se va a agregar al archivo de salida. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").  
  
## <a name="remarks"></a>Comentarios  

 Puede crear un archivo de recursos de Win32 con el compilador de recursos de Microsoft Windows.  
  
 Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayuda a identificar la aplicación en el **Explorador de Windows**. Si no se especifica `-win32resource`, el compilador generará información de versión basada en la versión del ensamblado. Las opciones `-win32resource` y `-win32icon` son mutuamente excluyentes.  
  
 Vea [-linkresource (Visual Basic)](linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o bien [-resource (Visual Basic)](resource.md) para adjuntar un archivo de recursos de .NET Framework.  
  
> [!NOTE]
> La opción `-win32resource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 El siguiente código compila `In.vb` y adjunta un archivo de recursos de Win32, `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
