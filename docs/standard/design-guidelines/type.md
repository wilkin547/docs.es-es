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
ms.openlocfilehash: af7511f4159fdbfe2d3f972dc927e9ee11fd586f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-design-guidelines"></a>Instrucciones de diseño de tipos
Desde la perspectiva CLR, hay solo dos categorías de tipos: tipos de referencia y tipos de valor, pero con el fin de obtener una explicación sobre el diseño de marco de trabajo, se dividen los tipos en grupos lógicos más, cada uno con sus propias reglas de diseño específicas.  
  
 Las clases son el caso general de los tipos de referencia. Constituyen la mayor parte de los tipos en la mayoría de los marcos de trabajo. Clases pendientes a su popularidad, para el conjunto de características orientadas a objetos que admiten datos completos y su aplicabilidad general. Clases base y clases abstractas son grupos lógicos especiales relacionadas con la extensibilidad.  
  
 Interfaces son tipos que pueden ser implementados por los tipos de referencia y tipos de valor. Por lo tanto pueden servir como raíces de polimórficas jerarquías de tipos de referencia y tipos de valor. Además, se pueden utilizar interfaces para simular la herencia múltiple, que no es compatible de forma nativa con CLR.  
  
 Las estructuras son el caso general de los tipos de valor y que debe reservarse para los tipos pequeños y sencillos, como primitivas del lenguaje.  
  
 Las enumeraciones son un caso especial de tipos de valor utilizados para definir cortos conjuntos de valores, como los días de la semana, los colores de consola y así sucesivamente.  
  
 Las clases estáticas son tipos que pretende ser contenedores para los miembros estáticos. Se suelen usar para proporcionar accesos directos a otras operaciones.  
  
 Delegados, excepciones, atributos, matrices y colecciones son todos los casos especiales de los tipos de referencia diseñados para usos específicos, y directrices de diseño y de uso se tratan en otro lugar en este libro.  
  
 **✓ HACER** Asegúrese de que cada tipo es un conjunto bien definido de miembros relacionados, no sólo un conjunto aleatorio de funcionalidad no relacionado.  
  
## <a name="in-this-section"></a>En esta sección  
 [Elección entre clase y estructura](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Diseño de clases abstractas](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md)  
 [Diseño de interfaces](../../../docs/standard/design-guidelines/interface.md)  
 [Diseño de estructuras](../../../docs/standard/design-guidelines/struct.md)  
 [Diseño de enumeraciones](../../../docs/standard/design-guidelines/enum.md)  
 [Tipos anidados](../../../docs/standard/design-guidelines/nested-types.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
