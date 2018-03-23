---
title: -addmodule
ms.date: 03/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c17d5541fe2d02ba88f4c5ef259b2248f371dfe5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-addmodule"></a>-addmodule
Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
 `fileList`  
 Requerido. Lista delimitada por comas de los archivos que contienen metadatos pero no contienen manifiestos de ensamblado. Nombres de archivo que contienen espacios deben ir entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 Los archivos mostrados por la `fileList` parámetro debe crearse con el `-target:module` opción, o con el equivalente de otro compilador a `-target:module`.  
  
 Todos los módulos agregados con `-addmodule` debe estar en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución. Si no es así, obtendrá una <xref:System.TypeLoadException> error.  
  
 Si especifica (implícita o explícitamente) cualquier[-destino (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opción distinto de `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` pasan a formar parte del ensamblado del proyecto. Se requiere un ensamblado para ejecutar un archivo de salida que tiene uno o más archivos agregados mediante `-addmodule`.  
  
 Use [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contiene un ensamblado.  
  
> [!NOTE]
>  El `-addmodule` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código crea un módulo.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 El siguiente código importa los tipos del módulo.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Al ejecutar `t1`, genera `802`.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
