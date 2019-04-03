---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 5dcf9dc5cc0987e965aba7fd2b8821252e19a655
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815997"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
Especifica el nombre del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`filename`|Obligatorio. El nombre del archivo de salida que crea el compilador. Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 Especifique el nombre completo y la extensión de archivo que se creará. Si no lo hace, el archivo .exe toma su nombre de archivo de código fuente que contiene el `Sub Main` procedimiento y el archivo .dll adopta el nombre del primer archivo de código fuente.  
  
 Si especifica un nombre de archivo sin extensión .exe o .dll, el compilador agrega automáticamente la extensión para usted, dependiendo del valor especificado para el `-target` opción del compilador.  
  
|Para establecer - out en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el **nombre del ensamblado** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y crea el archivo de salida `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
