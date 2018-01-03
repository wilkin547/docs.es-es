---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cdb7cff2221930113d6b49a640da0844f175f1b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="imports-visual-basic"></a>/imports (Visual Basic)
Importa los espacios de nombres desde un ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`namespaceList`|Requerido. Lista delimitada por comas de espacios de nombres que desea importar.|  
  
## <a name="remarks"></a>Comentarios  
 El `/imports` opción importa cualquier espacio de nombres definido dentro del conjunto actual de archivos de origen o de cualquier ensamblado que se hace referencia.  
  
 Los miembros de un espacio de nombres especificado con `/imports` están disponibles para todos los archivos de código fuente de la compilación. Utilice la [Imports (instrucción Namespace de .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para utilizar un espacio de nombres en un archivo de código fuente individual.  
  
|Para establecer/importa en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Referencias**.<br />3.  Escriba el nombre de espacio de nombres en la casilla situada junto a la **Agregar importación del usuario** botón.<br />4.  Haga clic en el **Agregar importación del usuario** botón.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila cuando `/imports:system` se especifica.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
