---
title: Obtener acceso a XML en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 79c7b8a94731e151a803a041d91dd1e240ddeb97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-xml-in-visual-basic"></a>Obtener acceso a XML en Visual Basic
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Proporciona propiedades de eje XML para obtener acceso y navegar por [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] estructuras. Estas propiedades utilizan una sintaxis especial que le permite tener acceso a elementos y atributos especificando los nombres XML.  
  
 En la tabla siguiente se enumera las características de lenguaje que permiten obtener acceso a elementos y atributos en XML [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
### <a name="xml-axis-properties"></a>Propiedades de eje XML  
  
|Descripción de la propiedad|Ejemplo|Descripción|  
|--------------------------|-------------|-----------------|  
|*eje child*|`contact.<phone>`|Obtiene todos los `phone` elementos que son elementos secundarios de la `contact` elemento.|  
|*eje de atributo*|`phone.@type`|Obtiene todos los `type` atributos de la `phone` elemento.|  
|*eje Descendant*|`contacts...<name>`|Obtiene todos los `name` elementos de la `contacts` elemento, independientemente de la profundidad de la jerarquía que se produzcan.|  
|*indizador de extensión*|`contacts...<name>(0)`|Obtiene la primera `name` elemento de la secuencia.|  
|*value*|`contacts...<name>.Value`|Obtiene la representación de cadena del primer objeto de la secuencia, o `Nothing` si la secuencia está vacía.|  
  
## <a name="in-this-section"></a>En esta sección  
 [Acceso a elementos descendientes XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen el nombre especificado y que están incluidos en un elemento XML especificado.  
  
 [Acceso a elementos secundarios XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Muestra cómo utilizar a un elemento secundario de la propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML.  
  
 [Acceso a atributos XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen el nombre especificado en un elemento XML.  
  
 [Declarar y usar prefijos de espacio de nombres XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y tener acceso a elementos XML.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Propiedades del eje XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Proporciona vínculos a secciones que describen las diversas propiedades de acceso XML.  
  
 [Información general sobre LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.  
  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Proporciona una introducción al uso de literales XML en Visual Basic.  
  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Proporciona vínculos a secciones sobre cómo cargar y modificar XML en Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Proporciona vínculos a secciones que describen cómo utilizar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.
