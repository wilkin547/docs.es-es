---
title: Acceso a XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351747"
---
# <a name="accessing-xml-in-visual-basic"></a>Obtener acceso a XML en Visual Basic
Visual Basic proporciona propiedades de eje XML para tener acceso a las estructuras de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] y navegar por ellas. Estas propiedades usan una sintaxis especial para permitir el acceso a elementos y atributos mediante la especificación de los nombres XML.  
  
 En la tabla siguiente se enumeran las características del lenguaje que permiten tener acceso a los elementos y atributos XML en Visual Basic.  
  
### <a name="xml-axis-properties"></a>Propiedades de eje XML  
  
|Descripción de la propiedad|Ejemplo|Descripción|  
|--------------------------|-------------|-----------------|  
|*eje secundario*|`contact.<phone>`|Obtiene todos los elementos de `phone` que son elementos secundarios del elemento `contact`.|  
|*eje de atributo*|`phone.@type`|Obtiene todos los atributos `type` del elemento `phone`.|  
|*eje descendiente*|`contacts...<name>`|Obtiene todos los elementos `name` del elemento `contacts`, independientemente de la profundidad de la jerarquía que se produzcan.|  
|*indexador de extensión*|`contacts...<name>(0)`|Obtiene el primer elemento `name` de la secuencia.|  
|*valor*|`contacts...<name>.Value`|Obtiene la representación de cadena del primer objeto de la secuencia o `Nothing` si la secuencia está vacía.|  
  
## <a name="in-this-section"></a>Esta sección  
 [Acceso a elementos descendientes XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML especificado.  
  
 [Acceso a elementos secundarios XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.  
  
 [Acceso a atributos XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen un nombre especificado en un elemento XML.  
  
 [Declarar y usar prefijos de espacio de nombres XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y obtener acceso a los elementos XML.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Propiedades del eje XML](../../../../visual-basic/language-reference/xml-axis/index.md)  
 Proporciona vínculos a secciones en las que se describen las distintas propiedades de acceso XML.  
  
 [Información general sobre LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Proporciona una introducción al uso de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.  
  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Proporciona una introducción al uso de literales XML en Visual Basic.  
  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Proporciona vínculos a las secciones sobre cómo cargar y modificar XML en Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Proporciona vínculos a secciones en las que se describe cómo usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.
