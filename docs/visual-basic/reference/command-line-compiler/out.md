---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005332"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Especifica el nombre del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|Obligatorio. Nombre del archivo de salida que crea el compilador. Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 Especifique el nombre completo y la extensión del archivo que se va a crear. Si no lo hace, el archivo. exe toma su nombre del archivo de código fuente que contiene el procedimiento `Sub Main` y el archivo. dll toma su nombre del primer archivo de código fuente.  
  
 Si especifica un nombre de archivo sin la extensión. exe o. dll, el compilador agrega automáticamente la extensión, en función del valor especificado para la opción del compilador `-target`.  
  
|Para establecer en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el cuadro **nombre de ensamblado** .|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y crea el archivo de salida `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
