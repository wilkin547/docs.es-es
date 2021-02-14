---
description: 'Más información acerca de: Métodos de extensión.'
title: Métodos de extensión
ms.date: 10/22/2008
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 2f71ec86252045687558bd61337164ac3afbcd20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642063"
---
# <a name="extension-methods"></a>Métodos de extensión

Los métodos de extensión son una característica de lenguaje que permite llamar a métodos estáticos mediante la sintaxis de llamada de método de instancia. Estos métodos deben tomar al menos un parámetro, que representa la instancia en la que operará el método.

 La clase que define tales métodos de extensión se conoce como la clase "patrocinador" y se debe declarar como estática. Para usar métodos de extensión, debe importar el espacio de nombres que define la clase patrocinador.

 ❌ EVITE definir frívolamente métodos de extensión, especialmente en tipos que no le pertenecen.

 Si posee el propio código fuente de un tipo, plantéese la posibilidad de usar métodos de instancia normales en su lugar. Si no es el propietario y desea agregar un método, tenga mucho cuidado. El uso liberal de los métodos de extensión tiene el potencial de saturar las API de los tipos que no se diseñaron para tener estos métodos.

 ✔️ PLANTÉESE la posibilidad de usar métodos de extensión en cualquiera de los escenarios siguientes:

- Para proporcionar una funcionalidad auxiliar relevante para cada implementación de una interfaz, si dicha funcionalidad se puede escribir en términos de la interfaz principal. Esto se debe a que las implementaciones concretas no pueden asignarse a interfaces de otro modo. Por ejemplo, los operadores `LINQ to Objects` se implementan como métodos de extensión para todos los tipos <xref:System.Collections.Generic.IEnumerable%601>. Por lo tanto, cualquier implementación de `IEnumerable<>` se habilita automáticamente para LINQ.

- Cuando un método de instancia introduciría una dependencia en algún tipo, pero tal dependencia rompería las reglas de administración de dependencias. Por ejemplo, una dependencia de <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> probablemente no sea deseable, por lo que el método de instancia `String.ToUri()` que devuelve `System.Uri` sería el diseño equivocado desde una perspectiva de administración de dependencias. Un método de extensión estático `Uri.ToUri(this string str)` que devuelve `System.Uri` sería un diseño mucho mejor.

 ❌ EVITE definir métodos de extensión en <xref:System.Object?displayProperty=nameWithType>.

 Los usuarios de VB no podrán llamar a estos métodos en referencias a objetos mediante la sintaxis del método de extensión. VB no admite la llamada a tales métodos porque, en VB, la declaración de una referencia como objeto obliga a que todas sus invocaciones de método estén enlazadas tardíamente (el miembro real llamado se determina en tiempo de ejecución), mientras que los enlaces a los métodos de extensión se determinan en tiempo de compilación (enlazados tempranamente).

 Tenga en cuenta que la instrucción se aplica a otros lenguajes en los que está presente el mismo comportamiento de enlace o donde no se admiten los métodos de extensión.

 ❌ NO coloque métodos de extensión en el mismo espacio de nombres que el tipo extendido a menos que sea para agregar métodos a interfaces o para la administración de dependencias.

 ❌ EVITE definir dos o más métodos de extensión con la misma firma, aunque residan en diferentes espacios de nombres.

 ✔️ PLANTÉESE la posibilidad de definir métodos de extensión en el mismo espacio de nombres que el tipo extendido si el tipo es una interfaz y si los métodos de extensión están diseñados para usarse en la mayoría de los casos o en todos ellos.

 ❌ NO defina métodos de extensión que implementen una característica en espacios de nombres que normalmente están asociados a otras características. En su lugar, defínalos en el espacio de nombres asociado a la característica a la que pertenecen.

 ❌ EVITE el nombre genérico de los espacios de nombres dedicados a métodos de extensión (por ejemplo, "Extensions"). En su lugar, use un nombre descriptivo (por ejemplo, "Enrutamiento").

 *Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
