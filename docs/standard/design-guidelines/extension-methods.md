---
title: Métodos de extensión.
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfc2e6def94d0830df4a4cdf738cdeef106de9f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180415"
---
# <a name="extension-methods"></a>Métodos de extensión.
Métodos de extensión son una característica del lenguaje que permite a los métodos estáticos llamar mediante sintaxis de llamada de método de instancia. Estos métodos deben tener al menos un parámetro, que representa la instancia en que es el método operar.  
  
 La clase que define estos métodos de extensión se conoce como la clase "patrocinador" y debe declararse como static. Para usar los métodos de extensión, uno debe importar el espacio de nombres de definición de la clase de patrocinador.  
  
 **X AVOID** frívolamente definir métodos de extensión, especialmente en tipos que no posee.  
  
 Si dispone de código fuente de un tipo, considere la posibilidad de usar los métodos de instancia normal en su lugar. Si no posee y desea agregar un método, tenga mucho cuidado. El uso racional de métodos de extensión tiene el potencial de saturar la API de tipos que no se diseñaron para estos métodos.  
  
 **✓ CONSIDER** mediante métodos de extensión en cualquiera de los siguientes escenarios:  
  
-   Para proporcionar la aplicación auxiliar de funcionalidad relevante para cada implementación de una interfaz, si dice funcionalidad puede escribirse en términos de la interfaz básica. Esto es porque las implementaciones concretas en caso contrario, no se puede asignar a las interfaces. Por ejemplo, el `LINQ to Objects` operadores se implementan como métodos de extensión para todos los <xref:System.Collections.Generic.IEnumerable%601> tipos. Por lo tanto, cualquier `IEnumerable<>` implementación es automáticamente habilitado para LINQ.  
  
-   Cuando un método de instancia introduce una dependencia en algún tipo, pero esta dependencia interrumpiría las reglas de administración de dependencia. Por ejemplo, una dependencia de <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> probablemente no es deseable de modo que `String.ToUri()` devolver el método de instancia `System.Uri` sería un diseño incorrecto desde una perspectiva de administración de dependencias. Un método de extensión estático `Uri.ToUri(this string str)` devolver `System.Uri` sería un mejor diseño.  
  
 **X AVOID** definir métodos de extensión en <xref:System.Object?displayProperty=nameWithType>.  
  
 Los usuarios VB no podrán llamar a dichos métodos en las referencias de objeto mediante la sintaxis de método de extensión. VB no admite llamar a dichos métodos porque, en VB, declarar una referencia como objeto obliga a todas las invocaciones de método en el que esté en tiempo de ejecución enlazado (miembro real denominado se determina en tiempo de ejecución), mientras que los enlaces a los métodos de extensión se determinan en tiempo de compilación (al principio enlazado).  
  
 Tenga en cuenta que el criterio se aplica a otros lenguajes, donde el mismo comportamiento de enlace está presente, o que no se admiten métodos de extensión.  
  
 **X DO NOT** colocar métodos de extensión en el mismo espacio de nombres como el tipo extendido a menos que sea para agregar métodos a interfaces o para la administración de dependencias.  
  
 **X AVOID** definir dos o más métodos de extensión con la misma firma, incluso si residen en diferentes espacios de nombres.  
  
 **✓ CONSIDER** definir métodos de extensión en el mismo espacio de nombres como el tipo extendido si el tipo es una interfaz y los métodos de extensión están diseñados para usarse en la mayoría de los casos.  
  
 **X DO NOT** definir métodos de extensión que se implementa una característica de espacios de nombres que normalmente se asocian con otras características. En su lugar, definirlos en el espacio de nombres asociado con la característica que pertenecen.  
  
 **X AVOID** genérico de nomenclatura de espacios de nombres dedicados a los métodos de extensión (por ejemplo, "extensiones"). Utilice un nombre descriptivo (por ejemplo, "enrutamiento") en su lugar.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
