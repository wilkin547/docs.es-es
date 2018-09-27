---
title: Generación de excepciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fbbe84811e3fa096b9e13c459143311bb75a198
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397912"
---
# <a name="exception-throwing"></a>Generación de excepciones
Excepciones directrices descritas en esta sección requieren una buena definición del significado del error de ejecución. Se produce un error de ejecución cada vez que un miembro no puede hacer lo que fue diseñado para hacer (lo que el nombre de miembro implica). Por ejemplo, si la `OpenFile` método no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.  
  
 La mayoría de los desarrolladores se han vuelto cómodos con el uso de excepciones para errores de uso como la división por cero o referencias nulas. En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.  
  
 **X DO NOT** devolver códigos de error.  
  
 Las excepciones son el medio principal para informar de errores en los marcos de trabajo.  
  
 **✓ DO** notificar errores de ejecución iniciando excepciones.  
  
 **✓ CONSIDER** la terminación del proceso mediante una llamada a `System.Environment.FailFast` (característica de .NET Framework 2.0) en lugar de producir una excepción si el código encuentra una situación donde no es seguro para la ejecución aún más.  
  
 **X DO NOT** usar excepciones para el flujo normal de control, si es posible.  
  
 Excepto para los errores del sistema y operaciones con posibles condiciones de carrera, los diseñadores de framework deberían diseñar las API para que los usuarios pueden escribir código que no inicia excepciones. Por ejemplo, puede proporcionar una manera de comprobar las condiciones previas antes de llamar a un miembro, por lo que los usuarios pueden escribir código que no inicia excepciones.  
  
 El miembro que se usa para comprobar las condiciones previas de otro miembro a menudo se conoce como una herramienta de comprobación y el miembro que hace realmente el trabajo se llama a una parte de la acción.  
  
 Hay casos Tester-Doer (modelo) puede tener una sobrecarga de rendimiento aceptable. En tales casos, se debe considerar el patrón de Try Parse llamados (consulte [excepciones y rendimiento](../../../docs/standard/design-guidelines/exceptions-and-performance.md) para obtener más información).  
  
 **✓ CONSIDER** las implicaciones de rendimiento de inicio de excepciones. Las tasas de throw superior a 100 por segundo están probables que afectar considerablemente al rendimiento de mayoría de las aplicaciones.  
  
 **✓ DO** documento todas las excepciones iniciadas por miembros invocables públicamente debido a una infracción del miembro del contrato (en lugar de un error del sistema) y tratan como parte de su contrato.  
  
 Las excepciones que forman parte del contrato no deben cambiar de una versión a la siguiente (es decir, no debe cambiar el tipo de excepción y no se deben agregar nuevas excepciones).  
  
 **X DO NOT** tener miembros públicos que pueden ya sea throw o no en función de alguna opción.  
  
 **X DO NOT** tiene miembros públicos que devuelven las excepciones como el valor devuelto o un `out` parámetro.  
  
 Devolver las excepciones de las API públicas en lugar de escribirlos frustra muchas de las ventajas de informe de errores basado en excepciones.  
  
 **✓ CONSIDER** mediante métodos de generador de excepciones.  
  
 Es habitual para producir la misma excepción desde distintos lugares. Para evitar el sobredimensionamiento del código, use métodos auxiliares que crean excepciones e inicializan sus propiedades.  
  
 Además, los miembros que se producen excepciones no obtienen insertadas. Mover la instrucción throw en el generador puede permitir que el miembro se puede insertar.  
  
 **X DO NOT** genere excepciones desde bloques de filtro de excepción.  
  
 Cuando un filtro de excepción produce una excepción, la excepción ha sido detectada por el CLR y el filtro devuelve false. Este comportamiento es indistinguible de la ejecución del filtro y devuelve false explícitamente y, por tanto, es muy difícil de depurar.  
  
 **X AVOID** iniciar explícitamente excepciones desde bloques finally. Las excepciones iniciadas implícitamente resultantes de llamar a métodos que inician son aceptables.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)
