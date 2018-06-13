---
title: Directivas de hoja de estilos incrustadas en un documento
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fa671304c611db571b160cd1d960b83bf451c9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569335"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>Directivas de hoja de estilos incrustadas en un documento
A veces, el documento XML contiene la directiva de hoja de estilos `<?xml:stylesheet?>`. Microsoft Internet Explorer lo acepta como alternativa a la sintaxis `<?xml-stylesheet?>`. Cuando los datos XML contienen una directiva `<?xml:stylesheet?>`, tal como se muestra en los datos siguientes, si se intentan cargar estos datos en el Modelo de objetos de documento XML (DOM), se inicia una excepción.  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Esto se produce porque `<?xml:stylesheet?>` se considera un nodo **ProcessingInstruction** no válido para DOM. Cualquier **ProcessingInstruction**, de acuerdo con la especificación XML de los espacios de nombres, solo puede ser un nombre que no incluya un signo de dos puntos (NCName), en contraposición a nombres calificados (QName).  
  
 Según la sección 6 acerca de los espacios de nombres de la especificación de XML, el efecto de los métodos **Load** y **LoadXml** que se ajustan a la especificación es que en un documento:  
  
-   Todos los tipos de elemento y nombres de atributo no contienen un signo de dos puntos o sólo contienen uno.  
  
-   Ningún nombre de entidad, destino ProcessingInstruction ni nombre de notación, contiene un signo de dos puntos.  
  
 Si `<?xml:stylesheet?>` contiene un signo de dos puntos, se infringe la regla de la segunda viñeta.  
  
 De acuerdo con la recomendación de la versión 1,0 de los documentos XML acerca de la asociación de hojas de estilos de W3C, que se encuentra en www.w3.org/TR/xml-stylesheet, la instrucción de procesamiento para asociar una hoja de estilos XSLT con un documento XML es `<?xml-stylesheet?>`, con un guión en lugar del signo de dos puntos.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
