---
title: "Procesar el archivo XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comentarios XML, analizar [Visual Basic]"
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Procesar el archivo XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El compilador genera una cadena id. por cada construcción del código marcada para generar documentación.  \(Para obtener información sobre cómo etiquetar el código, vea [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).\) La cadena id. identifica de forma exclusiva cada construcción.  Los programas que procesan el archivo XML pueden utilizar la cadena id. para identificar el elemento de metadatos o reflexión correspondiente en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
 El archivo XML no es una representación jerárquica del código, es una lista sencilla con un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas id.:  
  
-   No se coloca ningún espacio en blanco en la cadena.  
  
-   La primera parte de la cadena de id. identifica el tipo de miembro por medio de un único carácter seguido de dos puntos.  Se utilizan los siguientes tipos de miembros:  
  
|||  
|-|-|  
|Carácter|Descripción|  
|N|Espacio de nombres<br /><br /> No se pueden agregar comentarios de documentación a un espacio de nombres, pero, si se admiten, se pueden hacer referencias CREF a ellos.|  
|T|tipo: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|campo: `Dim`|  
|P|propiedad: `Property` \(incluidas las propiedades predeterminadas\)|  
|M|método: `Sub`, `Function`, `Declare`, `Operator`|  
|E|evento: `Event`|  
|\!|cadena de error<br /><br /> El resto de la cadena proporciona información acerca del error.  El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] genera información de error para los vínculos que no se pueden resolver.|  
  
-   La segunda parte de `String` es el nombre completo del elemento, que comienza en la raíz del espacio de nombres.  El nombre del elemento, los tipos contenedores y el espacio de nombres se separan mediante puntos.  Si el propio nombre del elemento contiene puntos, éstos se reemplazan por el signo \(\#\).  Se supone que ningún elemento contiene un signo \# directamente en su nombre.  Por ejemplo, el nombre completo del constructor de `String` sería `System.String.#ctor`.  
  
-   Para propiedades y métodos, si existen argumentos para el método, la lista de argumentos que se encuentra entre paréntesis aparece a continuación.  Si no existen argumentos, no se escribe ningún paréntesis.  Los argumentos se separan por comas.  La codificación de cada argumento indica directamente cómo se codifica en una firma de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
## Ejemplo  
 Los siguientes ejemplos muestran cómo se generarían las cadenas de id. para una clase y sus miembros:  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## Vea también  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Cómo: Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)