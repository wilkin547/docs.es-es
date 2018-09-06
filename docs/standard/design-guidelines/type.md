---
title: Instrucciones de diseño de tipos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7fb9964d0e542c0937c55ae65bd88b3f7149fa8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036030"
---
# <a name="type-design-guidelines"></a>Instrucciones de diseño de tipos
Desde la perspectiva CLR, hay solo dos categorías de tipos: tipos de referencia y tipos de valor, pero con el fin de obtener una explicación sobre el diseño de framework, dividimos tipos en grupos lógicos más, cada uno con sus propias reglas de diseño específicas.  
  
 Las clases son el caso general de los tipos de referencia. Constituyen la mayor parte de los tipos en la mayoría de los marcos de trabajo. Las clases deben su popularidad, para el amplio conjunto de características orientada a objetos que admiten y su aplicabilidad general. Clases abstractas y clases base son grupos lógicos especiales relacionadas con la extensibilidad.  
  
 Las interfaces son tipos que se pueden implementar por tipos de referencia y tipos de valor. Por lo tanto pueden servir como raíces de polimórficas jerarquías de tipos de referencia y tipos de valor. Además, las interfaces se pueden utilizar para simular la herencia múltiple, que no se admite de forma nativa por CLR.  
  
 Las estructuras son el caso general de los tipos de valor y se deben reservadas para los tipos pequeños y sencillas, como primitivas del lenguaje.  
  
 Las enumeraciones son un caso especial de tipos de valor utilizados para definir conjuntos corto de valores, como los días de la semana, los colores de consola y así sucesivamente.  
  
 Las clases estáticas son tipos que pretende ser contenedores para los miembros estáticos. Normalmente se utilizan para proporcionar accesos directos a otras operaciones.  
  
 Los delegados, excepciones, atributos, matrices y colecciones son todos los casos especiales de los tipos de referencia diseñados para usos específicos y directrices para su diseño y el uso se explican más adelante en este libro.  
  
 **✓ DO** Asegúrese de que cada tipo es un conjunto bien definido de miembros relacionados, no sólo un conjunto aleatorio de funcionalidad no relacionado.  
  
## <a name="in-this-section"></a>En esta sección  
 [Elección entre clase y estructura](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Diseño de clases abstractas](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md)  
 [Diseño de interfaces](../../../docs/standard/design-guidelines/interface.md)  
 [Diseño de estructuras](../../../docs/standard/design-guidelines/struct.md)  
 [Diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md)  
 [Tipos anidados](../../../docs/standard/design-guidelines/nested-types.md)  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
