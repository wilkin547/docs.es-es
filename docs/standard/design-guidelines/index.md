---
title: Instrucciones de diseño de .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2674acf14aae5e892dfb9707a19cca12b4797c90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572988"
---
# <a name="framework-design-guidelines"></a>Instrucciones de diseño de .NET Framework
Esta sección proporciona instrucciones de diseño de las bibliotecas que extensión e interactúan con .NET Framework. El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y facilidad de uso al proporcionar un modelo de programación unificado que es independiente del lenguaje de programación utilizado para el desarrollo. Se recomienda seguir estas directrices de diseño al desarrollar clases y componentes que extienden .NET Framework. Diseño de biblioteca incoherente afecta negativamente afecta a la productividad del desarrollador y desaconseja adopción.  
  
 Las instrucciones se organizan como recomendaciones sencillas precedidas con los términos de `Do`, `Consider`, `Avoid`, y `Do not`. Estas instrucciones están diseñadas para ayudar a los diseñadores de la biblioteca de clases a comprender las ventajas y desventajas de las distintas soluciones. Puede haber situaciones donde buen diseño de bibliotecas requiere que infringen estas directrices de diseño. Estos casos deben ser infrecuentes, y es importante que tenga una razón clara de peso para su decisión.  
  
 Estas instrucciones se ha extraído de la libreta de *directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición*, Krzysztof Cwalina y Brad Abrams.  
  
## <a name="in-this-section"></a>En esta sección  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Proporciona instrucciones para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros en bibliotecas de clases.  
  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 Proporciona instrucciones para utilizar clases estáticas y abstractas, interfaces, enumeraciones, estructuras y otros tipos.  
  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 Proporciona directrices para diseñar y utilizar propiedades, métodos, constructores, campos, eventos, operadores y parámetros.  
  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Describe los mecanismos de extensibilidad, como crear subclases de una, con eventos, los miembros virtuales y las devoluciones de llamada y explica cómo elegir los mecanismos que mejor cumplen los requisitos del marco de trabajo.  
  
 [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)  
 Describe las instrucciones de diseño para diseñar, producir y detectar excepciones.  
  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Describe las instrucciones para utilizar tipos comunes, como matrices, atributos y colecciones, admita la serialización y la sobrecarga de operadores de igualdad.  
  
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Proporciona directrices para elegir e implementar propiedades de dependencia y el patrón de dispose.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Información general](../../../docs/framework/get-started/overview.md)  
 [Guía básica de .NET Framework](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [Guía de desarrollo](../../../docs/framework/development-guide.md)
