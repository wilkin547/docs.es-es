---
title: Directivas de hoja de estilos incrustadas en un documento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>Directivas de hoja de estilos incrustadas en un documento
A veces, el documento XML contiene la directiva de hoja de estilos `<?xml:stylesheet?>`. Microsoft Internet Explorer lo acepta como alternativa a la `<?xml-stylesheet?>` sintaxis. Cuando los datos XML contienen una directiva `<?xml:stylesheet?>`, tal como se muestra en los datos siguientes, si se intentan cargar estos datos en el Modelo de objetos de documento XML (DOM), se inicia una excepción.  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Esto ocurre porque la `<?xml:stylesheet?>` se considera no válido **ProcessingInstruction** en el DOM. Cualquier **ProcessingInstruction**, según los espacios de nombres en la especificación XML, solo pueden ser nombres sin dos puntos (NCName), en contraposición a completo nombres (completos QName).  
  
 Desde la sección 6 acerca de los espacios de nombres en la especificación de XML, el efecto de tener la **carga** y **LoadXml** métodos se ajustan a la especificación es que en un documento:  
  
-   Todos los tipos de elemento y nombres de atributo no contienen un signo de dos puntos o sólo contienen uno.  
  
-   Ningún nombre de entidad, destino ProcessingInstruction ni nombre de notación, contiene un signo de dos puntos.  
  
 Si `<?xml:stylesheet?>` contiene un signo de dos puntos, se infringe la regla de la segunda viñeta.  
  
 De acuerdo con la recomendación de la versión 1,0 de los documentos XML acerca de la asociación de hojas de estilos de W3C, que se encuentra en www.w3.org/TR/xml-stylesheet, la instrucción de procesamiento para asociar una hoja de estilos XSLT con un documento XML es `<?xml-stylesheet?>`, con un guión en lugar del signo de dos puntos.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
