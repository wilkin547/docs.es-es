---
title: /Imports (Visual Basic) | Documentos de Microsoft
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
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
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
ms.openlocfilehash: 1dcbba442413dba63aef31fd40a511bad5e8217b
ms.lasthandoff: 03/13/2017

---
# <a name="imports-visual-basic"></a>/imports (Visual Basic)
Espacios de nombres se importa desde un ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`namespaceList`|Obligatorio. Lista delimitada por comas de espacios de nombres que desea importar.|  
  
## <a name="remarks"></a>Comentarios  
 El `/imports` opción importa cualquier espacio de nombres definido dentro del conjunto de archivos de origen o de cualquier ensamblado de referencia actual.  
  
 Los miembros de un espacio de nombres especificado con `/imports` están disponibles para todos los archivos de código fuente en la compilación. Utilice la [Imports (instrucción Namespace .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) utilizar un espacio de nombres en un archivo de código fuente individual.  
  
|Para establecer /Imports en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **referencias** ficha.<br />3.  Escriba el nombre de espacio de nombres en la casilla situada junto a la **Agregar importación del usuario** botón.<br />4.  Haga clic en el **Agregar importación del usuario** botón.|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila cuándo `/imports:system` especificado.  
  
 [!code-vb[21 VbVbalrCompiler](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
