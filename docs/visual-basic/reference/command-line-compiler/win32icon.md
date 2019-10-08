---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004633"
---
# <a name="-win32icon"></a>-win32icon
Inserta un archivo. ico en el archivo de salida. Este archivo. ico representa el archivo de salida en el **Explorador de archivos**.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|Archivo. ico que se va a agregar al archivo de salida. Escriba el nombre de archivo entre comillas ("") si contiene un espacio.|  
  
## <a name="remarks"></a>Comentarios  
 Puede crear un archivo. ico con el compilador de recursos de Microsoft Windows (RC). El compilador de recursos se invoca al compilar un programa visual C++ ; se crea un archivo. ICO a partir del archivo. rc. Las opciones `-win32icon` y `-win32resource` son mutuamente excluyentes.  
  
 Vea [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un archivo de recursos .NET Framework, o [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un archivo de recursos de .NET Framework. Vea [-Win32Resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) para importar un archivo. res.  
  
|Para Set-win32icon en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el cuadro **icono** .|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `In.vb` y adjunta un archivo. ico, `Rf.ico`.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
