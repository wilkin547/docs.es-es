---
title: Clases base para implementar abstracciones
ms.date: 10/22/2008
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: 314fcd0e1e91d1fc869453dd442ecaa72f91955d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821598"
---
# <a name="base-classes-for-implementing-abstractions"></a>Clases base para implementar abstracciones
En realidad, una clase se convierte en una clase base cuando se deriva otra clase de ella. En esta sección, sin embargo, una clase base es una clase diseñada principalmente para proporcionar una abstracción común o para que otras clases reutilicen alguna implementación predeterminada a través de la herencia. Las clases base normalmente se encuentran en medio de las jerarquías de herencia, entre una abstracción en la raíz de una jerarquía y varias implementaciones personalizadas en la parte inferior.

 Sirven como aplicaciones auxiliares de implementación para implementar abstracciones. Por ejemplo, una de las abstracciones del marco de trabajo para colecciones ordenadas de elementos es la <xref:System.Collections.Generic.IList%601> interfaz. La implementación de <xref:System.Collections.Generic.IList%601> no es trivial y, por tanto, el marco de trabajo proporciona varias clases base, como <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.Collections.ObjectModel.KeyedCollection%602> , que sirven de ayuda para implementar colecciones personalizadas.

 Las clases base no suelen ser adecuadas para servir como abstracciones por sí mismas, porque tienden a contener demasiada implementación. Por ejemplo, la `Collection<T>` clase base contiene una gran cantidad de implementación relacionada con el hecho de que implementa la `IList` interfaz no genérica (para integrar mejor con colecciones no genéricas) y el hecho de que es una colección de elementos almacenados en memoria en uno de sus campos.

 Como se explicó anteriormente, las clases base pueden proporcionar una ayuda valiosa para los usuarios que necesitan implementar abstracciones, pero al mismo tiempo pueden ser una responsabilidad importante. Agregan el área expuesta y aumentan la profundidad de las jerarquías de herencia y, por tanto, complican conceptualmente el marco. Por lo tanto, las clases base deben usarse solo si proporcionan un valor significativo a los usuarios del marco. Deben evitarse si proporcionan valor solo a los implementadores de Framework, en cuyo caso se debe tener en cuenta la delegación a una implementación interna en lugar de la herencia de una clase base.

 ✔️ considere la posibilidad de crear clases base abstractas aunque no contengan ningún miembro abstracto. Esto se comunica claramente a los usuarios de los que la clase está diseñada únicamente para su herencia.

 ✔️ considere la posibilidad de colocar las clases base en un espacio de nombres independiente de los tipos de escenario principal. Por definición, las clases base están pensadas para escenarios de extensibilidad avanzada y, por lo tanto, no son interesantes para la mayoría de los usuarios.

 ❌ Evite el nombre de las clases base con un sufijo "base" si la clase está pensada para su uso en las API públicas.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño de marco](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
