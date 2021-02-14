---
description: Más información acerca de cómo obtener acceso a XML en Visual Basic
title: Acceso a XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 2d77b2aa5f4136095ce5684976fe3ba03be7c28c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462664"
---
# <a name="accessing-xml-in-visual-basic"></a>Obtener acceso a XML en Visual Basic

Visual Basic proporciona propiedades de eje XML para tener acceso a las estructuras y navegar por ellas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . Estas propiedades usan una sintaxis especial para permitir el acceso a elementos y atributos mediante la especificación de los nombres XML.  
  
 En la tabla siguiente se enumeran las características del lenguaje que permiten tener acceso a los elementos y atributos XML en Visual Basic.  
  
### <a name="xml-axis-properties"></a>Propiedades de eje XML  
  
|Descripción de la propiedad|Ejemplo|Descripción|  
|--------------------------|-------------|-----------------|  
|*eje child*|`contact.<phone>`|Obtiene todos los `phone` elementos que son elementos secundarios del `contact` elemento.|  
|*eje de atributo*|`phone.@type`|Obtiene todos los `type` atributos del `phone` elemento.|  
|*eje descendant*|`contacts...<name>`|Obtiene todos los `name` elementos del `contacts` elemento, independientemente de la profundidad de la jerarquía en la que se producen.|  
|*indexador de extensión*|`contacts...<name>(0)`|Obtiene el primer `name` elemento de la secuencia.|  
|*value*|`contacts...<name>.Value`|Obtiene la representación en forma de cadena del primer objeto de la secuencia o `Nothing` si la secuencia está vacía.|  
  
## <a name="in-this-section"></a>En esta sección  

 [Procedimiento para obtener acceso a elementos descendientes XML](how-to-access-xml-descendant-elements.md)  
 Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML especificado.  
  
 [Procedimiento para obtener acceso a elementos secundarios XML](how-to-access-xml-child-elements.md)  
 Muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.  
  
 [Procedimiento para obtener acceso a atributos XML](how-to-access-xml-attributes.md)  
 Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen un nombre especificado en un elemento XML.  
  
 [Procedimiento para declarar y usar prefijos de espacio de nombres XML](how-to-declare-and-use-xml-namespace-prefixes.md)  
 Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y obtener acceso a los elementos XML.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Propiedades de eje XML](../../../language-reference/xml-axis/index.md)  
 Proporciona vínculos a secciones en las que se describen las distintas propiedades de acceso XML.  
  
 [Información general sobre LINQ to XML en Visual Basic](overview-of-linq-to-xml.md)  
 Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] de en Visual Basic.  
  
 [Crear XML en Visual Basic](creating-xml.md)  
 Proporciona una introducción al uso de literales XML en Visual Basic.  
  
 [Manipular XML en Visual Basic](manipulating-xml.md)  
 Proporciona vínculos a las secciones sobre cómo cargar y modificar XML en Visual Basic.  
  
 [XML](index.md)  
 Proporciona vínculos a secciones que describen cómo usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.
