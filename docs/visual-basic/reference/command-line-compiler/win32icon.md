---
description: Mas información sobre -win32icon
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 32a46771012708a42beb5450d28daf2fbab3f1c0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433554"
---
# <a name="-win32icon"></a>-win32icon

Inserta un archivo .ico en el archivo de salida. Este archivo .ico representa el archivo de salida en el **Explorador de archivos**.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|El archivo .ico que se va a agregar al archivo de salida. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").|  
  
## <a name="remarks"></a>Comentarios  

 Puede crear un archivo .ico con el Compilador de recursos (RC) de Microsoft Windows. El compilador de recursos se invoca al compilar un programa de Visual C++ y se crea un archivo .ico a partir del archivo .rc. Las opciones `-win32icon` y `-win32resource` son mutuamente excluyentes.  
  
 Vea [-linkresource (Visual Basic)](linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o bien [-resource (Visual Basic)](resource.md) para adjuntar un archivo de recursos de .NET Framework. Vea [-win32resource](win32resource.md) para importar un archivo .res.  
  
|Para establecer -win32icon en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el cuadro **Icono**.|  
  
## <a name="example"></a>Ejemplo  

 El código siguiente compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
