---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 57a81983278c26090c62995f4da55c5cbfd66047
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408678"
---
# <a name="-doc"></a>-doc
Procesa los comentarios de documentación generando un archivo XML.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-doc[+ | -]  
```

o  

```console
-doc:file  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. Si se especifica + o solo `-doc`, el compilador genera información de documentación y la coloca en un archivo XML. Especificar `-` es el equivalente a no especificar `-doc`, lo que causa que no se cree ninguna información de documentación.|  
|`file`|Es necesario si se usa `-doc:`. Especifica el archivo XML de salida, que se rellena con los comentarios de los archivos de código fuente de la compilación. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").|  
  
## <a name="remarks"></a>Comentarios  
 La opción `-doc` controla si el compilador genera un archivo XML que contiene los comentarios de documentación. Si usa la sintaxis `-doc:file`, el parámetro `file` especifica el nombre del archivo XML. Si usa `-doc` o `-doc+`, el compilador toma el nombre del archivo XML desde el archivo ejecutable o la biblioteca que el compilador va a crear. Si usa `-doc-` o no especifica la opción `-doc`, el compilador no crea un archivo XML.  
  
 En los archivos de código fuente, los comentarios de documentación pueden preceder a las siguientes definiciones:  
  
- Tipos definidos por el usuario como una [clase](../../language-reference/statements/class-statement.md) o una [interfaz](../../language-reference/statements/interface-statement.md)  
  
- Miembros, como un campo, un [evento](../../language-reference/statements/event-statement.md), una [propiedad](../../language-reference/statements/property-statement.md), una [función](../../language-reference/statements/function-statement.md) o una [subrutina](../../language-reference/statements/sub-statement.md).  
  
 Para usar el archivo XML generado con la característica [IntelliSense](/visualstudio/ide/using-intellisense) de Visual Studio, deje que el nombre del archivo XML sea igual que el del ensamblado que quiere admitir. Asegúrese de que el archivo XML se encuentra en el mismo directorio que el ensamblado, para que cuando se haga referencia al ensamblado en el proyecto de Visual Studio, también se encuentre el archivo .xml. Los archivos de documentación XML no son necesarios para que IntelliSense funcione para el código dentro de un proyecto o de los proyectos a los que el proyecto hace referencia.  
  
 A menos que compile con `-target:module`, el archivo XML contiene las etiquetas `<assembly></assembly>`. Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.  
  
 Vea [Etiquetas XML para comentarios](../../language-reference/xmldoc/index.md) para conocer las maneras de generar documentación a partir de comentarios en el código.  
  
|Para definir -doc en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Establezca el valor en el cuadro **Generar archivo de documentación XML**.|  
  
## <a name="example"></a>Ejemplo  
 Vea [Documentar el código con XML (Visual Basic)](../../programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Documentar el código con XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
