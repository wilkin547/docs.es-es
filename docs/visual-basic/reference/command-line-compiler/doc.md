---
title: /doc
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2490529b951ef6e583e3bfa54afced89c823e874
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="doc"></a>/doc
Procesa los comentarios de documentación generando un archivo XML.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. Especificar +, o simplemente `/doc`, hace que el compilador genera información de documentación y lo coloca en un archivo XML. Especificar `-` equivale a no especificar `/doc`, haciendo que se generará ninguna información de documentación.|  
|`file`|Es necesario si se usa `/doc:`. Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación. Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 El `/doc` opción controla si el compilador genera un archivo XML que contiene los comentarios de documentación. Si usas el `/doc:``file` sintaxis, la `file` parámetro especifica el nombre del archivo XML. Si usa `/doc` o `/doc+`, el compilador usa el nombre del archivo XML desde el archivo ejecutable o biblioteca que está creando el compilador. Si usa `/doc-` o no especifique el `/doc` opción, el compilador no crea un archivo XML.  
  
 En los archivos de código fuente, los comentarios de documentación pueden preceder a las definiciones siguientes:  
  
-   Definido por el usuario tipos, como un [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [(interfaz)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Miembros, como un campo, [eventos](../../../visual-basic/language-reference/statements/event-statement.md), [propiedad](../../../visual-basic/language-reference/statements/property-statement.md), [función](../../../visual-basic/language-reference/statements/function-statement.md), o [subrutina](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Para usar el archivo XML generado con el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) de características, supongamos que el nombre de archivo del archivo XML es el mismo que el ensamblado que desea admitir. Asegúrese de que el archivo XML está en el mismo directorio que el ensamblado para que cuando se hace referencia el ensamblado en el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] proyecto, se encuentra el archivo .xml así. Archivos de documentación XML no son necesarios para que IntelliSense funcione para un código dentro de un proyecto o dentro de los proyectos que se hace referencia a un proyecto.  
  
 A menos que se compila con `/target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`. Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.  
  
 Vea [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) maneras de generar documentación a partir de comentarios en el código.  
  
|Para establecer a /doc en Visual Studio integra el entorno de desarrollo|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Establezca el valor el **archivo de documentación XML generar** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 Vea [documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
