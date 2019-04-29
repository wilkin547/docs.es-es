---
title: Instrucciones de diseño de tipos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: KrzysztofCwalina
ms.openlocfilehash: 16f2a095f461a406eedbd2b34b0c91d3ac43bbe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650107"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
