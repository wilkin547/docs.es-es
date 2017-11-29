---
title: Clases base para implementar abstracciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8cd779dba0e7ce559e29af7b16bf04b3d0dc2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="base-classes-for-implementing-abstractions"></a>Clases base para implementar abstracciones
En realidad, una clase se convierte en una clase base cuando otra clase se deriva de él. Sin embargo, con el propósito de esta sección, una clase base es una clase que se han diseñado principalmente para proporcionar una abstracción común o para que otras clases volver a utilizar algunos implementación aunque la herencia predeterminada. Clases base normalmente se colocan en el medio de las jerarquías de herencia, entre una abstracción en la raíz de una jerarquía y varias implementaciones personalizadas en la parte inferior.  
  
 Sirven como aplicaciones auxiliares de implementación para implementar abstracciones. Por ejemplo, una de las abstracciones del marco de trabajo para colecciones ordenadas de elementos es el <xref:System.Collections.Generic.IList%601> interfaz. Implementar <xref:System.Collections.Generic.IList%601> no es trivial, y, por tanto, el marco de trabajo proporciona varias clases base, como <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.Collections.ObjectModel.KeyedCollection%602>, que sirven como aplicaciones auxiliares para implementar colecciones personalizadas.  
  
 Clases base normalmente no son adecuadas para que actúe como abstracciones por sí solos, ya que tienden a contienen demasiados implementación. Por ejemplo, el `Collection<T>` clase base contiene una gran cantidad de implementación relacionados con el hecho de que implementa la interfaz no genérica `IList` interfaz (para integrar mejor con colecciones no genéricas) y en el hecho de que es una colección de elementos almacenados en memoria en uno de sus campos.  
  
 Como se explicó anteriormente, las clases base pueden proporcionar ayuda inestimable para usuarios que necesitan para implementar abstracciones, pero al mismo tiempo pueden ser una responsabilidad importante. Agregan área expuesta y aumentar la profundidad de las jerarquías de herencia y por lo tanto conceptualmente complicar el marco de trabajo. Por lo tanto, las clases base deben usarse únicamente si proporcionan un valor significativo para los usuarios de la plataforma. Debería evitarse si proporcionan valor únicamente a los implementadores de framework, en el que la delegación caso a una implementación interna en lugar de la herencia de una clase base debe considerarse fuertemente.  
  
 **✓ Considere la posibilidad de** las clases base que hagan abstracta incluso si no contienen ningún miembro abstracto. Esto indica claramente a los usuarios que la clase está diseñada únicamente para que se puede heredar de.  
  
 **Considere la posibilidad de ✓** colocar las clases base en un espacio de nombres independiente de los tipos de escenario admitirán. Por definición, las clases base están pensadas para escenarios de extensibilidad avanzadas y, por tanto, no son interesantes para la mayoría de los usuarios.  
  
 **X evitar** nomenclatura de clases base con un sufijo "Base" si la clase está diseñada para su uso en las API públicas.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseñar para la extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
