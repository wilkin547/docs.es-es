---
description: 'Más información acerca de: Clases base para implementar abstracciones'
title: Clases base para implementar abstracciones
ms.date: 10/22/2008
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: 255891695583e36977663153b0ccac98b7fff4c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642349"
---
# <a name="base-classes-for-implementing-abstractions"></a>Clases base para implementar abstracciones

En realidad, una clase se convierte en una clase base cuando se deriva otra clase de ella. Para esta sección, sin embargo, una clase base es una clase diseñada principalmente para proporcionar una abstracción común o para que otras clases reutilicen alguna implementación predeterminada mediante herencia. Las clases base normalmente se encuentran en medio de las jerarquías de herencia, entre una abstracción en la raíz de una jerarquía y varias implementaciones personalizadas en la parte inferior.

 Además, sirven como asistentes de implementación para implementar abstracciones. Por ejemplo, una de las abstracciones del marco para colecciones ordenadas de elementos es la interfaz <xref:System.Collections.Generic.IList%601>. La implementación de <xref:System.Collections.Generic.IList%601> no es trivial y, por tanto, el marco proporciona varias clases base, como <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.Collections.ObjectModel.KeyedCollection%602>, que actúan como asistentes para implementar colecciones personalizadas.

 Las clases base no suelen ser adecuadas para funcionar como abstracciones por sí mismas, porque tienden a contener demasiada implementación. Por ejemplo, la clase base `Collection<T>` contiene una gran cantidad de implementación relacionada con el hecho de que implementa la interfaz `IList` no genérica (para integrarse mejor con colecciones no genéricas) y de que se trata de una colección de elementos almacenados en memoria en uno de sus campos.

 Como se explicó anteriormente, las clases base pueden proporcionar una ayuda valiosa para los usuarios que necesitan implementar abstracciones, pero al mismo tiempo pueden ser un lastre importante. El motivo es que agregan un área expuesta y aumentan la profundidad de las jerarquías de herencia y, por tanto, complican conceptualmente el marco. Por lo tanto, las clases base deben usarse solo si proporcionan un valor significativo a los usuarios del marco. Deben evitarse si proporcionan valor solo a los implementadores del marco, en cuyo caso se debería usar la delegación a una implementación interna en lugar de la herencia de una clase base.

 ✔️ Recomendamos crear clases base abstractas aunque no contengan ningún miembro abstracto. Esto comunica claramente a los usuarios que la clase está diseñada únicamente para heredarse.

 ✔️ Recomendamos colocar las clases base en un espacio de nombres independiente de los tipos de escenario principal. Por definición, las clases base están pensadas para escenarios de extensibilidad avanzada y, por lo tanto, no son interesantes para la mayoría de los usuarios.

 ❌ EVITE denominar a las clases base con un sufijo "Base" si la clase está pensada para utilizarse en las API públicas.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
