---
title: Instrucciones de diseño de .NET Framework
description: Vea directrices de diseño del marco para diseñar bibliotecas que extienden e interactúan con .NET, para garantizar la coherencia de la API y la facilidad de uso.
titleSuffix: ''
ms.date: 10/22/2008
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 9dc764492e1ac565c51d49d07e6566295bb76bc1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821039"
---
# <a name="framework-design-guidelines"></a>Instrucciones de diseño de .NET Framework
En esta sección se proporcionan instrucciones para diseñar bibliotecas que extienden e interactúan con el .NET Framework. El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y la facilidad de uso, ya que proporciona un modelo de programación unificado que es independiente del lenguaje de programación usado para el desarrollo. Se recomienda seguir estas directrices de diseño al desarrollar clases y componentes que extienden el .NET Framework. El diseño incoherente de la biblioteca afecta negativamente a la productividad del desarrollador y desaconseja la adopción.  
  
 Las instrucciones se organizan como recomendaciones sencillas precedidas de los términos `Do` ,, `Consider` `Avoid` y `Do not` . Estas instrucciones están diseñadas para ayudar a los diseñadores de biblioteca de clases a comprender las ventajas e inconvenientes entre las distintas soluciones. Puede haber situaciones en las que el diseño de la biblioteca sea adecuado, ya que se infringen estas directrices de diseño. Estos casos deben ser raros y es importante que tenga una razón clara y convincente para su decisión.  
  
 Estas instrucciones se exforman de las *directrices de diseño de marcos de libros: convenciones, expresiones y patrones para bibliotecas de .net reutilizables, 2ª edición*, por Krzysztof Cwalina y Brad Abrams.  
  
## <a name="in-this-section"></a>En esta sección  
 [Instrucciones de nomenclatura](naming-guidelines.md)  
 Proporciona instrucciones para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros de las bibliotecas de clases.  
  
 [Instrucciones de diseño de tipos](type.md)  
 Proporciona instrucciones para el uso de clases, interfaces, enumeraciones, estructuras y otros tipos estáticos y abstractos.  
  
 [Instrucciones para el diseño de miembros](member.md)  
 Proporciona instrucciones para diseñar y usar propiedades, métodos, constructores, campos, eventos, operadores y parámetros.  
  
 [Diseñar extensibilidad](designing-for-extensibility.md)  
 Describe los mecanismos de extensibilidad, como las subclases, el uso de eventos, miembros virtuales y devoluciones de llamada, y explica cómo elegir los mecanismos que mejor satisfagan los requisitos de su marco de trabajo.  
  
 [Instrucciones de diseño de excepciones](exceptions.md)  
 Describe las directrices de diseño para diseñar, iniciar y detectar excepciones.  
  
 [Instrucciones de uso](usage-guidelines.md)  
 Describe las instrucciones para usar tipos comunes como matrices, atributos y colecciones, la compatibilidad con la serialización y la sobrecarga de operadores de igualdad.  
  
 [Modelos de diseño comunes](common-design-patterns.md)  
 Proporciona instrucciones para elegir e implementar propiedades de dependencia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Información general](../../framework/get-started/overview.md)
- [Guía de desarrollo](../../framework/development-guide.md)
