---
title: Clases base para implementar abstracciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f326ee895251678c7a23ea84a11e83951edf2cc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194882"
---
# <a name="base-classes-for-implementing-abstractions"></a>Clases base para implementar abstracciones
En realidad, una clase se convierte en una clase base cuando otra clase se deriva. Sin embargo, con el propósito de esta sección, una clase base es una clase que se han diseñado principalmente para proporcionar una abstracción común o para que otras clases reutilizar parte implementación aunque herencia predeterminada. Las clases base normalmente se colocan en el medio de las jerarquías de herencia entre una abstracción en la raíz de una jerarquía y varias implementaciones personalizadas en la parte inferior.  
  
 Actúan como aplicaciones auxiliares de implementación para implementar abstracciones. Por ejemplo, una de las abstracciones de .NET Framework para colecciones ordenadas de elementos es el <xref:System.Collections.Generic.IList%601> interfaz. Implementar <xref:System.Collections.Generic.IList%601> no es trivial, y por lo tanto, el marco de trabajo proporciona varias clases bases, como <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.Collections.ObjectModel.KeyedCollection%602>, que sirven como aplicaciones auxiliares para implementar colecciones personalizadas.  
  
 Las clases base normalmente no son adecuadas para que actúe como abstracciones por sí mismos, porque tienden a contener demasiada implementación. Por ejemplo, el `Collection<T>` clase base contiene una gran cantidad de implementación relacionada con el hecho de que implementa la interfaz no genérica `IList` interfaz (para integrarse mejor con las colecciones no genéricas) y al hecho de que es una colección de elementos almacenados en memoria en uno de sus campos.  
  
 Como se dijo anteriormente, las clases base pueden proporcionar ayuda inestimable para usuarios que necesitan para implementar abstracciones, pero al mismo tiempo pueden ser una responsabilidad importante. Agregar área de superficie y como aumentar la profundidad de las jerarquías de herencia y por lo que conceptualmente complicar el marco de trabajo. Por lo tanto, las clases base deben usarse únicamente si proporcionan un valor significativo a los usuarios de framework. Debe evitarse si proporciona el valor solo a los implementadores de framework, en el que caso delegación a una implementación interna en lugar de herencia de una clase base debe tener en cuenta.  
  
 **✓ CONSIDER** las clases base que hagan abstracta incluso si no contienen ningún miembro abstracto. Esto indica claramente a los usuarios que la clase está diseñada exclusivamente para heredar de.  
  
 **✓ CONSIDER** colocar las clases base en un espacio de nombres independiente de los tipos de escenario admitirán. Por definición, las clases base están pensadas para escenarios de extensibilidad avanzados y, por tanto, no son interesantes para la mayoría de los usuarios.  
  
 **X AVOID** nomenclatura de clases base con un sufijo "Base" si la clase está diseñada para su uso en las API públicas.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
