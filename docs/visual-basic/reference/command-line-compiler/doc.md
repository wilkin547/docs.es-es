---
title: /doc | Documentos de Microsoft
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
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
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
ms.openlocfilehash: 1054eb256eb7670ee0454b02fc094e0306c1218d
ms.lasthandoff: 03/13/2017

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
|`+` &#124; `-`|Opcional. Especifica +, o simplemente `/doc`, hace que el compilador generará información de documentación y colocarlo en un archivo XML. Especificar `-` equivale a no especificar `/doc`, no causando se crea ninguna información de documentación.|  
|`file`|Es necesario si se usa `/doc:`. Especifica el archivo XML de salida, que se llena con los comentarios de los archivos de código fuente de la compilación. Si el nombre de archivo contiene un espacio, encierre el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 El `/doc` opción controla si el compilador genera un archivo XML que contiene los comentarios de documentación. Si utiliza la `/doc:``file` sintaxis, el `file` parámetro especifica el nombre del archivo XML. Si utiliza `/doc` o `/doc+`, el compilador toma el nombre del archivo XML del archivo ejecutable o biblioteca que está creando el compilador. Si utiliza `/doc-` o no especifique el `/doc` opción, el compilador no crea un archivo XML.  
  
 En los archivos de código fuente, los comentarios de documentación pueden preceder a las definiciones siguientes:  
  
-   Definido por el usuario tipos, como un [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [(interfaz)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Miembros, como un campo, [eventos](../../../visual-basic/language-reference/statements/event-statement.md), [propiedad](../../../visual-basic/language-reference/statements/property-statement.md), [función](../../../visual-basic/language-reference/statements/function-statement.md), o [subrutina](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Para utilizar el archivo XML generado con la [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) de funciones, que el nombre de archivo del archivo XML es el mismo que el ensamblado que desea admitir. Asegúrese de que el archivo XML está en el mismo directorio que el ensamblado para que cuando se hace referencia al ensamblado en el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] proyecto, el archivo .xml se encuentra también. Archivos de documentación XML no son necesarios para que IntelliSense funcione para un código dentro de un proyecto o dentro de los proyectos que se hace referencia a un proyecto.  
  
 A menos que se compile con `/target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`. Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.  
  
 Consulte [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) formas de generar documentación a partir de los comentarios en el código.  
  
|Para establecer a /doc en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Establezca el valor de la **generar archivo de documentación** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 Consulte [documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
