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
ms.openlocfilehash: 7a493e6591d90ce05a652e48807f63fa90764a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573726"
---
# <a name="exception-throwing"></a>Generación de excepciones
Generación de excepciones directrices descritas en esta sección requieren una buena definición del significado del error de ejecución. Se produce un error de ejecución cada vez que un miembro no puede hacer lo que estaba diseñado para hacer (lo que el nombre de miembro implica). Por ejemplo, si la `OpenFile` método no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.  
  
 Mayoría de los desarrolladores han familiarizado con excepciones para los errores de uso como la división por cero o referencias nulas. En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.  
  
 **X DO NOT** devolver códigos de error.  
  
 Las excepciones son el medio principal de informar de errores en los marcos de trabajo.  
  
 **✓ HACER** notificar errores de ejecución iniciando excepciones.  
  
 **✓ Considere la posibilidad de** la terminación del proceso mediante una llamada a `System.Environment.FailFast` (característica de .NET Framework 2.0) en lugar de producir una excepción si el código encuentra una situación donde no es seguro para la ejecución aún más.  
  
 **X DO NOT** usar excepciones para el flujo normal de control, si es posible.  
  
 Salvo los errores del sistema y operaciones con posibles condiciones de carrera, diseñadores de marco de trabajo deberían diseñar las API para que los usuarios puedan escribir código que no produce excepciones. Por ejemplo, puede proporcionar un mecanismo para comprobar las condiciones previas antes de llamar a un miembro, por lo que los usuarios puedan escribir código que no produce excepciones.  
  
 El miembro que se usa para comprobar las condiciones previas de otro miembro a menudo se conoce como una herramienta de comprobación y el miembro que hace realmente el trabajo se denomina una acción.  
  
 Hay casos en el patrón de acción de evaluador puede tener una sobrecarga de rendimiento inaceptable. En tales casos, debe considerarse el patrón de Try-análisis denominadas (vea [excepciones y rendimiento](../../../docs/standard/design-guidelines/exceptions-and-performance.md) para obtener más información).  
  
 **✓ Considere la posibilidad de** las implicaciones de rendimiento de inicio de excepciones. Las tasas de throw por encima de 100 por segundo son propensos a afectar notablemente el rendimiento de la mayoría de las aplicaciones.  
  
 **✓ HACER** documento todas las excepciones iniciadas por miembros invocables públicamente debido a una infracción del miembro del contrato (en lugar de un error del sistema) y tratan como parte de su contrato.  
  
 Las excepciones que forman parte del contrato no deberían cambiar de una versión a la siguiente (es decir, no debería cambiar el tipo de excepción y no se deben agregar nuevas excepciones).  
  
 **X DO NOT** tener miembros públicos que pueden ya sea throw o no en función de alguna opción.  
  
 **X DO NOT** tiene miembros públicos que devuelven las excepciones como el valor devuelto o un `out` parámetro.  
  
 Devolver las excepciones de las API públicas en lugar de producir ellos frustra muchas de las ventajas de informe de errores basado en excepciones.  
  
 **✓ Considere la posibilidad de** mediante métodos de generador de excepciones.  
  
 Es común para que se produzca la misma excepción desde distintos lugares. Para evitar la cantidad de código, use métodos auxiliares que crean excepciones e inicializan sus propiedades.  
  
 Además, los miembros que producen excepciones no obtienen entre líneas. Mover la instrucción throw en el generador puede permitir que el miembro se inserte.  
  
 **X DO NOT** genere excepciones desde bloques de filtro de excepción.  
  
 Cuando un filtro de excepción produce una excepción, se detecta la excepción de CLR y el filtro devuelve false. Este comportamiento es indistinguible desde que el filtro se ejecuta y devuelve false explícitamente y por lo tanto, es muy difícil de depurar.  
  
 **X evitar** iniciar explícitamente excepciones desde bloques finally. Las excepciones iniciadas implícitamente resultante de la llamada a métodos que inician son aceptables.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)
