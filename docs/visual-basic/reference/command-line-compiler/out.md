---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352387"
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
|1. tener un proyecto seleccionado en **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2. Haga clic en la pestaña **aplicación** .<br />3. modifique el valor en el cuadro **nombre de ensamblado** .|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `T2.vb` y crea `T2.exe`de archivo de salida.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
