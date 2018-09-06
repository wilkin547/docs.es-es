---
title: Tipos anidados
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2593b85dd4747a3fbe365994c3e5d9beae3e3406
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891545"
---
# <a name="nested-types"></a>Tipos anidados
Un tipo anidado es un tipo definido dentro del ámbito de otro tipo, que se denomina el tipo envolvente. Un tipo anidado tiene acceso a todos los miembros de su tipo envolvente. Por ejemplo, tiene acceso a campos privados, definidos en el tipo envolvente y que va a proteger los campos definidos en todos los antecesores del tipo envolvente.  
  
 En general, los tipos anidados deben usarse con moderación. Hay varias razones para ello. Algunos desarrolladores no están completamente familiarizados con el concepto. Estos desarrolladores por ejemplo, podrían tener problemas con la sintaxis de declaración de variables de tipos anidados. Los tipos anidados son también muy estrechamente con sus tipos envolventes y, por lo tanto no son adecuados para los tipos de uso general.  
  
 Los tipos anidados son más adecuados para el modelado de los detalles de implementación de sus tipos envolventes. El usuario final rara vez deberían tener que declarar variables de un tipo anidado y casi nunca debe crear explícitamente instancias de tipos anidados. Por ejemplo, el enumerador de una colección puede ser un tipo anidado de esa colección. Normalmente se crean instancias de los enumeradores por su tipo envolvente, y dado que muchos lenguajes admiten la instrucción foreach, variables de enumerador rara vez tienen que ser declarados por el usuario final.  
  
 **✓ DO** utilice tipos anidados cuando la relación entre el tipo anidado y su tipo exterior es tal que es deseable la semántica de accesibilidad de miembros.  
  
 **X DO NOT** use los tipos anidados públicos como una agrupación lógica construir; usar espacios de nombres para este.  
  
 **X AVOID** exponer públicamente los tipos anidados. La única excepción a esto es si las variables del tipo anidado que deben declararse sólo en escenarios poco frecuentes, como el uso de subclases u otros escenarios de personalización avanzada.  
  
 **X DO NOT** utilice tipos anidados si el tipo es probable que se hace referencia fuera del tipo contenedor.  
  
 Por ejemplo, una enumeración que se pasa a un método definido en una clase no debe definirse como un tipo anidado en la clase.  
  
 **X DO NOT** utilice tipos anidados si necesitan que se creará una instancia de un código de cliente.  Si un tipo tiene un constructor público, probablemente no debería estar anidado.  
  
 Si un tipo se puede crear instancias, que parece indicar que el tipo tiene un lugar en el marco de trabajo por sí mismo (puede crearla, trabajar con ellos y destruir sin necesidad de utilizar el tipo externo) y, por tanto, no se pueden anidar. No se deben reutilizar ampliamente internos tipos fuera del tipo externo sin ninguna relación con el tipo externo.  
  
 **X DO NOT** definir un tipo anidado como un miembro de una interfaz. Muchos lenguajes no admiten este tipo de construcción.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
