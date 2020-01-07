---
title: Métodos de extensión.
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: ad78bae2dc7a3000b67224da6f1a8c578053087f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347030"
---
# <a name="extension-methods"></a>Métodos de extensión.
Los métodos de extensión son una característica de lenguaje que permite llamar a métodos estáticos mediante la sintaxis de llamada al método de instancia. Estos métodos deben tomar al menos un parámetro, que representa la instancia en la que se va a operar el método.  
  
 La clase que define estos métodos de extensión se conoce como la clase "patrocinador" y se debe declarar como estática. Para usar métodos de extensión, debe importar el espacio de nombres que define la clase de patrocinador.  
  
 **X AVOID** frívolamente definir métodos de extensión, especialmente en tipos que no posee.  
  
 Si hace su propio código fuente de un tipo, considere la posibilidad de usar métodos de instancia normales en su lugar. Si no es de su propiedad y desea agregar un método, tenga mucho cuidado. El uso liberal de los métodos de extensión tiene el potencial de saturar las API de los tipos que no se diseñaron para tener estos métodos.  
  
 **✓ CONSIDER** mediante métodos de extensión en cualquiera de los siguientes escenarios:  
  
- Para proporcionar una funcionalidad auxiliar relevante para cada implementación de una interfaz, si se puede escribir la funcionalidad en términos de la interfaz principal. Esto se debe a que, de lo contrario, las implementaciones concretas no se pueden asignar a interfaces. Por ejemplo, los operadores de `LINQ to Objects` se implementan como métodos de extensión para todos los tipos de <xref:System.Collections.Generic.IEnumerable%601>. Por lo tanto, cualquier implementación de `IEnumerable<>` se habilita automáticamente para LINQ.  
  
- Cuando un método de instancia introduciría una dependencia en algún tipo, pero dicha dependencia interrumpiría las reglas de administración de dependencias. Por ejemplo, es probable que una dependencia de <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> no sea deseable, por lo que `String.ToUri()` método de instancia que devuelve `System.Uri` sería el diseño equivocado desde una perspectiva de administración de dependencias. Un método de extensión estático `Uri.ToUri(this string str)` devolver `System.Uri` sería un diseño mucho mejor.  
  
 **X AVOID** definir métodos de extensión en <xref:System.Object?displayProperty=nameWithType>.  
  
 Visual Basic usuarios no podrán llamar a estos métodos en referencias a objetos mediante la sintaxis del método de extensión. Visual Basic no admite la llamada a tales métodos porque, en Visual Basic, la declaración de una referencia como objeto obliga a todas las invocaciones de método en que se enlazan en tiempo de ejecución (el miembro real llamado se determina en tiempo de ejecución), mientras que los enlaces a los métodos de extensión se determinan en tiempo de compilación (enlazado en tiempo de compilación).  
  
 Tenga en cuenta que la instrucción se aplica a otros idiomas en los que está presente el mismo comportamiento de enlace o donde no se admiten los métodos de extensión.  
  
 **X DO NOT** colocar métodos de extensión en el mismo espacio de nombres como el tipo extendido a menos que sea para agregar métodos a interfaces o para la administración de dependencias.  
  
 **X AVOID** definir dos o más métodos de extensión con la misma firma, incluso si residen en diferentes espacios de nombres.  
  
 **✓ CONSIDER** definir métodos de extensión en el mismo espacio de nombres como el tipo extendido si el tipo es una interfaz y los métodos de extensión están diseñados para usarse en la mayoría de los casos.  
  
 **X DO NOT** definir métodos de extensión que se implementa una característica de espacios de nombres que normalmente se asocian con otras características. En su lugar, se deben definir en el espacio de nombres asociado a la característica a la que pertenecen.  
  
 **X AVOID** genérico de nomenclatura de espacios de nombres dedicados a los métodos de extensión (por ejemplo, "extensiones"). En su lugar, use un nombre descriptivo (por ejemplo, "enrutamiento").  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
