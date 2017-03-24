---
title: Obtener acceso a XML en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 215f057f0b4d884369aad53cbbdbb98f240b56c4
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-xml-in-visual-basic"></a>Obtener acceso a XML en Visual Basic
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona propiedades de eje XML para obtener acceso y navegar por [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] estructuras. Estas propiedades usan una sintaxis especial que le permite tener acceso a elementos y atributos especificando los nombres XML.  
  
 La tabla siguiente enumeran las características del lenguaje que permiten obtener acceso a elementos y atributos de XML [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="xml-axis-properties"></a>Propiedades de eje XML  
  
|Descripción de la propiedad|Ejemplo|Descripción|  
|--------------------------|-------------|-----------------|  
|*eje secundario*|`contact.<phone>`|Obtiene todos los `phone` elementos que son elementos secundarios de la `contact` elemento.|  
|*eje de atributo*|`phone.@type`|Obtiene todos los `type` atributos de la `phone` elemento.|  
|*eje descendiente*|`contacts...<name>`|Obtiene todos los `name` elementos de la `contacts` elemento, independientemente de la profundidad de la jerarquía que se producen.|  
|*indizador de extensión*|`contacts...<name>(0)`|Obtiene la primera `name` elemento de la secuencia.|  
|*value*|`contacts...<name>.Value`|Obtiene la representación de cadena del primer objeto de la secuencia, o `Nothing` si la secuencia está vacía.|  
  
## <a name="in-this-section"></a>En esta sección  
 [Acceso a elementos descendientes XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Muestra cómo utilizar una propiedad de eje descendiente para obtener acceso a todos los elementos XML que tienen el nombre especificado y están incluidos en un elemento XML especificado.  
  
 [Acceso a elementos secundarios XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Muestra cómo utilizar a un elemento secundario en la propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML.  
  
 [Acceso a atributos XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Muestra cómo utilizar una propiedad de eje de atributo para obtener acceso a todos los atributos XML que tienen el nombre especificado en un elemento XML.  
  
 [Declarar y usar prefijos de espacio de nombres XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y tener acceso a los elementos XML.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Propiedades del eje XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Proporciona vínculos a secciones que describen las diversas propiedades de acceso XML.  
  
 [Información general de LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Proporciona una introducción al uso de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] en Visual Basic.  
  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Proporciona una introducción al uso de literales XML en Visual Basic.  
  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Proporciona vínculos a secciones sobre cómo cargar y modificar XML en Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Proporciona vínculos a secciones que describen cómo utilizar [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] en Visual Basic.
