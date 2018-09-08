---
title: Diseño de constructores
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ad920c8028b102a13fdfe928d21768538e25b0f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180454"
---
# <a name="constructor-design"></a>Diseño de constructores
Hay dos tipos de constructores: escriba los constructores y los constructores de instancia.  
  
 Constructores de tipos son estáticos y se ejecutan en el CLR antes de utilizar el tipo. Constructores de instancias se ejecutan cuando se crea una instancia de un tipo.  
  
 Constructores de tipos no toman ningún parámetro. Constructores de instancias pueden. Constructores de instancias que no toman ningún parámetro se denominan a menudo los constructores predeterminados.  
  
 Los constructores son la forma más natural para crear instancias de un tipo. La mayoría de los desarrolladores buscará y pruebe a utilizar un constructor antes de que consideran modos alternativos de creación de instancias (por ejemplo, los métodos de fábrica).  
  
 **✓ CONSIDER** proporcionar simple, lo ideal es que el valor predeterminado, constructores.  
  
 Un constructor simple tiene un número muy pequeño de parámetros, y todos los parámetros son tipos primitivos o enumeraciones. Estos constructores simple aumentan la usabilidad de framework.  
  
 **✓ CONSIDER** mediante un método de generador estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si no parece natural siguiendo las directrices de diseño del constructor.  
  
 **✓ DO** usar los parámetros de constructor como accesos directos para establecer las propiedades principales.  
  
 No debería haber ninguna diferencia semántica entre mediante el constructor vacío seguido de algunos conjuntos de propiedades y utilizando un constructor con varios argumentos.  
  
 **✓ DO** utilizar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros del constructor se utilizan simplemente para establecer la propiedad.  
  
 La única diferencia entre estos parámetros y las propiedades debe ser las mayúsculas y minúsculas.  
  
 **✓ DO** un trabajo mínimo en el constructor.  
  
 Los constructores no deben hacer mucho trabajo que no sea la captura de los parámetros del constructor. El costo de cualquier otro procesamiento debe retrasarse hasta que es necesario.  
  
 **✓ DO** genere excepciones desde los constructores de instancia, si procede.  
  
 **✓ DO** declarar explícitamente el constructor predeterminado público en clases, si se requiere un constructor de ese tipo.  
  
 Si no declara ningún constructor en un tipo explícitamente, muchos lenguajes (por ejemplo, C#) agregará automáticamente un constructor predeterminado público. (Las clases abstractas obtención un constructor protegido).  
  
 Agregando un constructor con parámetros a una clase, impide que el compilador agregue el constructor predeterminado. Esto hace que a menudo cambios accidentales.  
  
 **X AVOID** la definición explícita de constructores predeterminados en estructuras.  
  
 Esto acelera la creación de una matriz, porque si no se define el constructor predeterminado, no tiene que ejecutarse en todas las ranuras de la matriz. Tenga en cuenta que muchos compiladores, incluidos C# no permite que las estructuras tienen constructores sin parámetros por este motivo.  
  
 **X AVOID** al llamar a los miembros virtuales en un objeto dentro de su constructor.  
  
 Una llamada a un miembro virtual hará que la invalidación más derivada que se llame, aunque el constructor del tipo más derivado no totalmente ejecutado todavía.  
  
### <a name="type-constructor-guidelines"></a>Instrucciones de Constructor de tipos  
 **✓ DO** hacer privado static (constructores).  
  
 Un constructor estático, que también se denomina un constructor de clase, se usa para inicializar un tipo. CLR llama al constructor estático antes de crea la primera instancia del tipo o se llama a los miembros estáticos en ese tipo. El usuario no tiene control sobre cuando se llama al constructor estático. Si un constructor estático no es privado, se puede llamar mediante código distinto de CLR. Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado. El compilador de C# obliga a los constructores estáticos para ser privado.  
  
 **X DO NOT** genere excepciones desde constructores estáticos.  
  
 Si se produce una excepción desde un constructor de tipo, el tipo no es utilizable en el dominio de aplicación actual.  
  
 **✓ CONSIDER** inicializar campos estáticos en línea, en lugar de utilizar explícitamente constructores estáticos, como el tiempo de ejecución se puede optimizar el rendimiento de tipos que no tienen un constructor estático definido explícitamente.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
