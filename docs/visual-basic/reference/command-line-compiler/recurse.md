---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a>/recurse
Compila archivos de código fuente de todos los subdirectorios del directorio especificado o el directorio del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumentos  
 `dir`  
 Opcional. El directorio en el que quiere que comience la búsqueda. Si no se especifica, la búsqueda comienza en el directorio del proyecto.  
  
 `file`  
 Obligatorio. Los archivos que buscará. Se admiten los caracteres comodín.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `/recurse`. Si no se especifica ningún nombre de archivo de salida, el compilador utilizará el nombre de archivo de salida en el primer archivo de entrada. Por lo general, suele ser el primer archivo en la lista de archivos compilados ordenada alfabéticamente. Por esta razón, es mejor especificar un archivo de salida mediante la `/out` opción.  
  
> [!NOTE]
>  El `/recurse` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila todos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el directorio actual.  
  
```  
vbc *.vb  
```  
  
 El siguiente código compila todos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] archivos en el `Test\ABC` directory y los directorios por debajo de él y, a continuación, genera `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [entrada/salida (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
