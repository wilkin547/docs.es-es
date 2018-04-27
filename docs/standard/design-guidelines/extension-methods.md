---
title: métodos de extensión.
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6247b6d1718f43d4b05d585cc12a05c5e0cc2035
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="extension-methods"></a>métodos de extensión.
Métodos de extensión son una característica del lenguaje que permite a los métodos estáticos llamarlo con la sintaxis de llamada de método de instancia. Estos métodos deben tener al menos un parámetro, que representa la instancia en que es el método operar.  
  
 La clase que define estos métodos de extensión se conoce como la clase "patrocinador" y se debe declarar como static. Para usar los métodos de extensión, uno debe importar el espacio de nombres que define la clase de patrocinador.  
  
 **X evitar** frívolamente definir métodos de extensión, especialmente en tipos que no posee.  
  
 Si tiene código fuente de un tipo, considere la posibilidad de usar los métodos de instancia en su lugar. Si no posee y desea agregar un método, tenga mucho cuidado. El uso racional de métodos de extensión tiene el potencial de ocupar las API de tipos que no se diseñaron para que estos métodos.  
  
 **✓ Considere la posibilidad de** mediante métodos de extensión en cualquiera de los siguientes escenarios:  
  
-   Para proporcionar auxiliar funcionalidad pertinente para cada implementación de una interfaz, si dice funcionalidad puede escribirse en cuanto a la interfaz básica. Esto es porque las implementaciones concretas en caso contrario, no se puede asignar a las interfaces. Por ejemplo, el `LINQ to Objects` operadores se implementan como métodos de extensión para todos los <xref:System.Collections.Generic.IEnumerable%601> tipos. Por lo tanto, cualquier `IEnumerable<>` implementación está habilitado automáticamente para LINQ.  
  
-   Cuando un método de instancia introduce una dependencia en algún tipo, pero esta dependencia interrumpiría las reglas de administración de dependencia. Por ejemplo, una dependencia de <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> probablemente no es deseable de modo que `String.ToUri()` devolver el método de instancia `System.Uri` sería el diseño incorrecto de una perspectiva de administración de dependencia. Un método de extensión estática `Uri.ToUri(this string str)` devolver `System.Uri` sería un mejor diseño.  
  
 **X evitar** definir métodos de extensión en <xref:System.Object?displayProperty=nameWithType>.  
  
 Los usuarios VB no podrán llamar a dichos métodos en las referencias de objeto mediante la sintaxis de método de extensión. VB no admite llamar a dichos métodos porque, en VB, declarar una referencia como objeto obliga a todas las invocaciones de método en el que se va a tiempo de ejecución enlazado (miembro real denominado se determina en tiempo de ejecución), mientras que los enlaces a los métodos de extensión se determinan en tiempo de compilación (al principio enlaza).  
  
 Tenga en cuenta que la regla se aplica a otros idiomas en el mismo comportamiento de enlace está presente, o que no se admiten métodos de extensión.  
  
 **X DO NOT** colocar métodos de extensión en el mismo espacio de nombres como el tipo extendido a menos que sea para agregar métodos a interfaces o para la administración de dependencias.  
  
 **X evitar** definir dos o más métodos de extensión con la misma firma, incluso si residen en diferentes espacios de nombres.  
  
 **✓ Considere la posibilidad de** definir métodos de extensión en el mismo espacio de nombres como el tipo extendido si el tipo es una interfaz y los métodos de extensión están diseñados para usarse en la mayoría de los casos.  
  
 **X DO NOT** definir métodos de extensión que se implementa una característica de espacios de nombres que normalmente se asocian con otras características. En su lugar, definirlos en el espacio de nombres asociado a la característica que pertenecen.  
  
 **X evitar** genérico de nomenclatura de espacios de nombres dedicados a los métodos de extensión (por ejemplo, "extensiones"). Utilice un nombre descriptivo (por ejemplo, "enrutamiento") en su lugar.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
