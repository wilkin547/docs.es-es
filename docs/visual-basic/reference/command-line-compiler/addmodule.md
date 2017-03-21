---
title: /addmodule | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 949962905ec933dc42301bf8c21654e73dbe2f70
ms.lasthandoff: 03/13/2017

---
# <a name="addmodule"></a>/addmodule
Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
 `fileList`  
 Obligatorio. Lista delimitada por comas de archivos que contienen metadatos pero no contienen manifiestos de ensamblado. Los nombres de archivo que contienen espacios deben incluirse entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 Los archivos mostrados por la `fileList` parámetro debe crearse con el `/target:module` opción, o con el equivalente de otro compilador a `/target:module`.  
  
 Todos los módulos agregados con `/addmodule` deben estar en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución. Si no es así, obtendrá una <xref:System.TypeLoadException>error.</xref:System.TypeLoadException>  
  
 Si se especifica (implícita o explícitamente) cualquier[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opción distinto de `/target:module` con `/addmodule`, los archivos que pase a `/addmodule` pasan a formar parte del ensamblado del proyecto. Es necesario un ensamblado para ejecutar un archivo de salida que tiene uno o más archivos agregados mediante `/addmodule`.  
  
 Utilice [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contiene un ensamblado.  
  
> [!NOTE]
>  El `/addmodule` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código crea un módulo.  
  
 [!code-vb[VbVbalrCompiler&#47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 El siguiente código importa los tipos del módulo.  
  
 [!code-vb[VbVbalrCompiler Nº&48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Al ejecutar `t1`, genera `802`.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
