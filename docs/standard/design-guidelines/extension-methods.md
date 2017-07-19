---
title: "m&#233;todos de extensi&#243;n. | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# m&#233;todos de extensi&#243;n.
Métodos de extensión son una característica del lenguaje que permite a los métodos estáticos para llamarse usando la sintaxis de llamada de método de instancia. Estos métodos deben realizar al menos un parámetro que representa la instancia operar en el método.  
  
 La clase que define estos métodos de extensión se conoce como la clase "patrocinador" y se debe declarar como static. Para usar los métodos de extensión, uno debe importar el espacio de nombres que define la clase de patrocinador.  
  
 **Evitar X** frívolamente definir métodos de extensión, especialmente en tipos que no posee.  
  
 Si dispone de código fuente de un tipo, considere la posibilidad de usar los métodos de instancia en su lugar. Si no posee y desea agregar un método, tenga mucho cuidado. El uso racional de métodos de extensión tiene el potencial de saturar las API de tipos que no se diseñaron para que estos métodos.  
  
 **✓, considere la posibilidad de** mediante métodos de extensión en cualquiera de los siguientes escenarios:  
  
-   Para proporcionar ayuda funcionalidad relevante para cada implementación de una interfaz, si dice funcionalidad puede escribirse en términos de la interfaz principal. Esto es porque las implementaciones concretas de lo contrario no se puede asignar a las interfaces. Por ejemplo, el `LINQ to Objects` operadores se implementan como métodos de extensión para todos los <xref:System.Collections.Generic.IEnumerable%601> tipos. Por lo tanto, cualquier `IEnumerable<>` implementación es automáticamente habilitado para LINQ.  
  
-   Cuando un método de instancia introduce una dependencia de tipo, pero esta dependencia interrumpiría las reglas de administración de dependencia. Por ejemplo, una dependencia de <xref:System.String> a <xref:System.Uri?displayProperty=fullName> probablemente no es deseable por lo que `String.ToUri()` devuelve el método de instancia `System.Uri` sería el diseño incorrecto desde una perspectiva de administración de dependencia. Un método de extensión estática `Uri.ToUri(this string str)` devolver `System.Uri` sería un mejor diseño.  
  
 **Evitar X** definir métodos de extensión en <xref:System.Object?displayProperty=fullName>.  
  
 Los usuarios VB no podrán llamar a dichos métodos en las referencias de objeto mediante la sintaxis del método de extensión. VB no admite llamar a dichos métodos porque, en VB, declarar una referencia como objeto obliga a todas las invocaciones de método en él para llegar tarde enlazado \(miembro real denominado se determina en tiempo de ejecución\), mientras que los enlaces a los métodos de extensión se determinan en tiempo de compilación \(enlazada tempranamente\).  
  
 Tenga en cuenta que la regla se aplica a otros idiomas en el mismo comportamiento de enlace está presente, o donde no se admiten métodos de extensión.  
  
 **X no** colocar métodos de extensión en el mismo espacio de nombres como el tipo extendido a menos que sea para agregar métodos a las interfaces o para la administración de dependencias.  
  
 **Evitar X** definir dos o más métodos de extensión con la misma firma, incluso si residen en diferentes espacios de nombres.  
  
 **✓ considere** definir métodos de extensión en el mismo espacio de nombres como el tipo extendido si el tipo es una interfaz y los métodos de extensión están diseñados para utilizarse en la mayoría de los casos.  
  
 **X no** definir la implementación de una característica de espacios de nombres que normalmente se asocian con otras características de los métodos de extensión. En su lugar, definirlos en el espacio de nombres asociado a la característica que pertenecen.  
  
 **Evitar X** nomenclatura genérica de espacios de nombres dedicado a los métodos de extensión \(por ejemplo, "extensiones"\). Utilice un nombre descriptivo \(por ejemplo, "enrutamiento"\) en su lugar.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)