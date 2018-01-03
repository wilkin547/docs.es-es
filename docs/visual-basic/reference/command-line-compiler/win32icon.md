---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4fc5210d2dcf30d9c4603b67b890c78510af1338
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="win32icon"></a>/win32icon
Inserta un archivo .ico en el archivo de salida. Este archivo .ico representa el archivo de salida en **Explorador de archivos**.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|El archivo .ico para agregar al archivo de salida. Ponga el nombre de archivo entre comillas ("") si contiene un espacio.|  
  
## <a name="remarks"></a>Comentarios  
 Puede crear un archivo .ico con el compilador de recursos de Microsoft Windows (RC). El compilador de recursos se invoca cuando se compila un programa de Visual C++; se crea un archivo .ico en el archivo .rc. El `/win32icon` y `/win32resource` opciones son mutuamente excluyentes.  
  
 Vea [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos. Vea [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) para importar un archivo. res.  
  
|Para establecer /win32icon en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el **icono** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
