---
title: Métodos de extensión
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 55e6a816bbec401fdb061a3394635378b2f37424
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621605"
---
# <a name="extension-methods"></a>Métodos de extensión
Los métodos de extensión son una característica de lenguaje que permite llamar a métodos estáticos mediante la sintaxis de llamada al método de instancia. Estos métodos deben tomar al menos un parámetro, que representa la instancia en la que se va a operar el método.

 La clase que define estos métodos de extensión se conoce como la clase "patrocinador" y se debe declarar como estática. Para usar métodos de extensión, debe importar el espacio de nombres que define la clase de patrocinador.

 ❌Evite la definición de métodos de extensión frivolously, especialmente en los tipos que no posee.

 Si hace su propio código fuente de un tipo, considere la posibilidad de usar métodos de instancia normales en su lugar. Si no es de su propiedad y desea agregar un método, tenga mucho cuidado. El uso liberal de los métodos de extensión tiene el potencial de saturar las API de los tipos que no se diseñaron para tener estos métodos.

 ✔️ considere la posibilidad de usar métodos de extensión en cualquiera de los escenarios siguientes:

- Para proporcionar una funcionalidad auxiliar relevante para cada implementación de una interfaz, si se puede escribir la funcionalidad en términos de la interfaz principal. Esto se debe a que, de lo contrario, las implementaciones concretas no se pueden asignar a interfaces. Por ejemplo, los `LINQ to Objects` operadores se implementan como métodos de extensión para todos los <xref:System.Collections.Generic.IEnumerable%601> tipos. Por lo tanto, cualquier `IEnumerable<>` implementación se habilita automáticamente para Linq.

- Cuando un método de instancia introduciría una dependencia en algún tipo, pero dicha dependencia interrumpiría las reglas de administración de dependencias. Por ejemplo, es probable que una dependencia de <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> sea no deseable y, por tanto, `String.ToUri()` el método de instancia que devuelve `System.Uri` sería un diseño equivocado desde una perspectiva de administración de dependencias. Un método de extensión `Uri.ToUri(this string str)` estático `System.Uri` que devuelve sería un diseño mucho mejor.

 ❌Evite definir métodos de extensión en <xref:System.Object?displayProperty=nameWithType> .

 Los usuarios de VB no podrán llamar a estos métodos en referencias a objetos mediante la sintaxis del método de extensión. VB no admite la llamada a tales métodos porque, en VB, la declaración de una referencia como objeto obliga a todas las invocaciones de método en él a enlazarse en tiempo de ejecución (el miembro real llamado se determina en tiempo de ejecución), mientras que los enlaces a los métodos de extensión se determinan en tiempo de compilación (enlazado en tiempo de compilación).

 Tenga en cuenta que la instrucción se aplica a otros idiomas en los que está presente el mismo comportamiento de enlace o donde no se admiten los métodos de extensión.

 ❌No coloque métodos de extensión en el mismo espacio de nombres que el tipo extendido a menos que sea para agregar métodos a interfaces o para la administración de dependencias.

 ❌Evite definir dos o más métodos de extensión con la misma firma, aunque residan en diferentes espacios de nombres.

 ✔️ considere la posibilidad de definir métodos de extensión en el mismo espacio de nombres que el tipo extendido si el tipo es una interfaz y si los métodos de extensión están diseñados para usarse en la mayoría o en todos los casos.

 ❌NO defina métodos de extensión que implementen una característica de en espacios de nombres que normalmente están asociados a otras características de. En su lugar, se deben definir en el espacio de nombres asociado a la característica a la que pertenecen.

 ❌Evite el nombre genérico de los espacios de nombres dedicados a métodos de extensión (por ejemplo, "extensiones"). En su lugar, use un nombre descriptivo (por ejemplo, "enrutamiento").

 *Partes &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones para el diseño de miembros](member.md)
- [Directrices de diseño de marco](index.md)
