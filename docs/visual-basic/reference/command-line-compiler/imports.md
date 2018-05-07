---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 330a5e6821c9c76f3503a35a5a5eabf24c686b42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
Importa los espacios de nombres desde un ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`namespaceList`|Requerido. Lista delimitada por comas de espacios de nombres que desea importar.|  
  
## <a name="remarks"></a>Comentarios  
 El `-imports` opción importa cualquier espacio de nombres definido dentro del conjunto actual de archivos de origen o de cualquier ensamblado que se hace referencia.  
  
 Los miembros de un espacio de nombres especificado con `-imports` están disponibles para todos los archivos de código fuente de la compilación. Utilice la [Imports (instrucción Namespace de .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para utilizar un espacio de nombres en un archivo de código fuente individual.  
  
|Para establecer/importa en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Referencias**.<br />3.  Escriba el nombre de espacio de nombres en la casilla situada junto a la **Agregar importación del usuario** botón.<br />4.  Haga clic en el **Agregar importación del usuario** botón.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila cuando `/imports:system.globalization` se especifica. Sin él, compilación correcta requiere que una `Imports System.Globalization` instrucción se incluye al principio del archivo de código fuente, o que la propiedad totalmente calificarse como `System.Globalization.CultureInfo.CurrentCulture.Name`. 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
