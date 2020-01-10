---
title: Tipos anidados
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: 3467851aa767efcd0557e8a412cd36316a48b9b0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709158"
---
# <a name="nested-types"></a>Tipos anidados
Un tipo anidado es un tipo definido dentro del ámbito de otro tipo, que se denomina tipo envolvente. Un tipo anidado tiene acceso a todos los miembros de su tipo envolvente. Por ejemplo, tiene acceso a los campos privados definidos en el tipo envolvente y a los campos protegidos definidos en todos los antecesores del tipo envolvente.  
  
 En general, los tipos anidados deben usarse con moderación. Hay varias razones para ello. Algunos desarrolladores no están totalmente familiarizados con el concepto. Por ejemplo, estos desarrolladores pueden tener problemas con la sintaxis de declarar variables de tipos anidados. Los tipos anidados también están estrechamente acoplados a sus tipos envolventes y, por lo tanto, no son adecuados para ser tipos de uso general.  
  
 Los tipos anidados son idóneos para modelar los detalles de implementación de los tipos envolventes. El usuario final no suele tener que declarar variables de un tipo anidado y casi nunca debe tener que crear explícitamente instancias de tipos anidados. Por ejemplo, el enumerador de una colección puede ser un tipo anidado de esa colección. Normalmente se crea una instancia de los enumeradores por su tipo envolvente, y dado que muchos lenguajes admiten la instrucción foreach, las variables de enumerador rara vez deben declararse por el usuario final.  
  
 **✓ DO** utilice tipos anidados cuando la relación entre el tipo anidado y su tipo exterior es tal que es deseable la semántica de accesibilidad de miembros.  
  
 **X DO NOT** use los tipos anidados públicos como una agrupación lógica construir; usar espacios de nombres para este.  
  
 **X AVOID** exponer públicamente los tipos anidados. La única excepción a esto se debe a que las variables del tipo anidado solo deben declararse en escenarios poco frecuentes, como subclases u otros escenarios de personalización avanzados.  
  
 **X DO NOT** utilice tipos anidados si el tipo es probable que se hace referencia fuera del tipo contenedor.  
  
 Por ejemplo, una enumeración que se pasa a un método definido en una clase no debe definirse como un tipo anidado en la clase.  
  
 **X DO NOT** utilice tipos anidados si necesitan que se creará una instancia de un código de cliente.  Si un tipo tiene un constructor público, probablemente no se debe anidar.  
  
 Si se puede crear una instancia de un tipo, parece que el tipo tiene un lugar en el marco por su cuenta (puede crearlo, trabajar con él y destruirlo sin usar el tipo externo) y, por tanto, no debe estar anidado. Los tipos internos no se deben reutilizar ampliamente fuera del tipo externo sin ninguna relación en absoluto con el tipo externo.  
  
 **X DO NOT** definir un tipo anidado como un miembro de una interfaz. Muchos lenguajes no admiten este tipo de construcción.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
