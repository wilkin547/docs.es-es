---
title: / recurse | Documentos de Microsoft
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
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fbf7d67c7f70345e62ddbb03c8626b688b5c593b
ms.lasthandoff: 03/13/2017

---
# <a name="recurse"></a>/recurse
Compila archivos de código fuente de todos los subdirectorios del directorio especificado o el directorio del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumentos  
 `dir`  
 Opcional. El directorio en el que desea iniciar la búsqueda. Si no se especifica, la búsqueda comienza en el directorio del proyecto.  
  
 `file`  
 Obligatorio. Los archivos para buscar. Se permiten caracteres comodín.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin utilizar `/recurse`. Si no se especifica ningún nombre de archivo de salida, el compilador utilizará el nombre de archivo de salida en el primer archivo de entrada. Suele ser el primer archivo en la lista de archivos compilados ordenada alfabéticamente. Por este motivo, es mejor especificar un archivo de salida con el `/out` opción.  
  
> [!NOTE]
>  El `/recurse` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila todos [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] archivos en el directorio actual.  
  
```  
vbc *.vb  
```  
  
 El siguiente código compila todos [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] archivos en el `Test\ABC` directory y los directorios y, a continuación, genera `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
