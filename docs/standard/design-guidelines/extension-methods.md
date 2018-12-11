---
title: Métodos de extensión.
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: 6fedd41e901035290995d7ece1b5aa23e76f345e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148302"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
