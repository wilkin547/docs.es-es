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
ms.openlocfilehash: 6c0eca851746899654636d36dce679acffc07ef0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="nested-types"></a>Tipos anidados
Un tipo anidado es un tipo definido en el ámbito de otro tipo, que se denomina el tipo envolvente. Un tipo anidado tiene acceso a todos los miembros de su tipo envolvente. Por ejemplo, tiene acceso a los campos privados definidos en el tipo envolvente y proteger los campos definidos en todos los antecesores del tipo envolvente.  
  
 En general, los tipos anidados deben usarse con moderación. Hay varias razones para ello. Algunos desarrolladores no están totalmente familiarizados con el concepto. Por ejemplo, estos desarrolladores tenga problemas con la sintaxis de la declaración de variables de tipos anidados. Los tipos anidados son también muy estrechamente con sus tipos envolventes y como tal no son adecuados para ser tipos de uso generales.  
  
 Los tipos anidados son más adecuados para modelar los detalles de implementación de sus tipos envolventes. El usuario final rara vez deberían tener que declarar las variables de un tipo anidado y casi nunca debería tener que crear explícitamente instancias de tipos anidados. Por ejemplo, el enumerador de una colección puede ser un tipo anidado de dicha recopilación. Normalmente se crean instancias de los enumeradores por su tipo envolvente, y dado que muchos lenguajes admiten la instrucción foreach, variables de enumerador rara vez tienen que ser declarada por el usuario final.  
  
 **✓ HACER** utilice tipos anidados cuando la relación entre el tipo anidado y su tipo exterior es tal que es deseable la semántica de accesibilidad de miembros.  
  
 **X DO NOT** use los tipos anidados públicos como una agrupación lógica construir; usar espacios de nombres para este.  
  
 **X evitar** exponer públicamente los tipos anidados. La única excepción a esto es si las variables del tipo anidado deben declararse sólo en escenarios poco habituales, como el uso de subclases u otros escenarios de personalización avanzada.  
  
 **X DO NOT** utilice tipos anidados si el tipo es probable que se hace referencia fuera del tipo contenedor.  
  
 Por ejemplo, una enumeración que se pasa a un método definido en una clase no debe definirse como un tipo anidado en la clase.  
  
 **X DO NOT** utilice tipos anidados si necesitan que se creará una instancia de un código de cliente.  Si un tipo tiene un constructor público, probablemente no debería anidarse.  
  
 Si un tipo se puede crear instancias, que parece indicar el tipo tiene un lugar en el marco de trabajo por sí misma (puede crearla, trabajar con ellos y destruir sin necesidad de utilizar el tipo exterior) y, por tanto, no se pueden anidar. Tipos internos no se deberían reutilizar ampliamente fuera del tipo externo sin ninguna relación con el tipo exterior.  
  
 **X DO NOT** definir un tipo anidado como un miembro de una interfaz. Muchos lenguajes no admiten este tipo de construcción.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
