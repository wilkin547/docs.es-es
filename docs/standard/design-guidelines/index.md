---
title: Instrucciones de diseño de .NET Framework
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
ms.openlocfilehash: c20430f9cdcd71cc2e178d38aeed48f9fa4e75c5
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834903"
---
# <a name="framework-design-guidelines"></a>Instrucciones de diseño de .NET Framework
Esta sección proporciona directrices para diseñar bibliotecas que extenderán e interactúan con .NET Framework. El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y facilidad de uso, ya que proporciona un modelo de programación unificado que es independiente del lenguaje de programación usado para el desarrollo. Se recomienda que siga estas directrices de diseño al desarrollar clases y componentes que extiendan .NET Framework. Diseño de la biblioteca incoherente negativamente afecta a la productividad del desarrollador y disuaden del adopción.  
  
 Las instrucciones se organizan como recomendaciones sencillas precedidas por los términos `Do`, `Consider`, `Avoid`, y `Do not`. Estas instrucciones están pensadas para ayudar a los diseñadores de bibliotecas de clase a comprender las ventajas y desventajas entre las distintas soluciones. Puede haber situaciones donde buen diseño de bibliotecas requiere que infringen estas directrices de diseño. Estos casos deberían ser excepcionales y es importante que tenga un motivo claro y atractivo para su decisión.  
  
 Estas instrucciones son un extracto de la libreta de *instrucciones de diseño de Framework: Convenciones, expresiones y patrones para las bibliotecas reutilizables. NET, 2ª edición*, Krzysztof Cwalina y Brad Abrams.  
  
## <a name="in-this-section"></a>En esta sección  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Proporciona directrices para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros en las bibliotecas de clases.  
  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 Proporciona instrucciones para utilizar clases estáticas y abstractas, interfaces, enumeraciones, estructuras y otros tipos.  
  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 Proporciona directrices para diseñar y usar las propiedades, métodos, constructores, campos, eventos, operadores y parámetros.  
  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Explica los mecanismos de extensibilidad, como la creación de subclases, mediante eventos, los miembros virtuales y las devoluciones de llamada y cómo elegir los mecanismos que satisfagan los requisitos del marco de trabajo.  
  
 [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)  
 Describe las instrucciones de diseño para diseñar, iniciar y detectar excepciones.  
  
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Describe las instrucciones para el uso de tipos comunes, como matrices, atributos y colecciones, admitir la serialización y la sobrecarga de operadores de igualdad.  
  
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Proporciona directrices para elegir e implemente las propiedades de dependencia.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Información general](../../../docs/framework/get-started/overview.md)
- [Guía de desarrollo](../../../docs/framework/development-guide.md)
