---
title: Generación de excepciones
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: d41467b971e43ca9b22c59e3b64bdd45d16c740b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734405"
---
# <a name="exception-throwing"></a>Generación de excepciones

Las instrucciones de generación de excepciones descritas en esta sección requieren una buena definición del significado del error de ejecución. El error de ejecución se produce siempre que un miembro no puede hacer lo que se diseñó (lo que implica el nombre de miembro). Por ejemplo, si el `OpenFile` método no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.

 La mayoría de los desarrolladores se han familiarizado con el uso de excepciones para errores de uso como la división por cero o referencias nulas. En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.

 ❌ NO devuelva códigos de error.

 Las excepciones son el medio principal para informar de errores en marcos de trabajo.

 ✔️ los errores de ejecución de informes iniciando excepciones.

 ✔️ considere la posibilidad de finalizar el proceso mediante una llamada a `System.Environment.FailFast` (característica .NET Framework 2,0) en lugar de iniciar una excepción si el código encuentra una situación en la que no es seguro para la ejecución posterior.

 ❌ No utilice excepciones para el flujo de control normal, si es posible.

 A excepción de los errores del sistema y las operaciones con posibles condiciones de carrera, los diseñadores de Marcos deben diseñar las API para que los usuarios puedan escribir código que no produzca excepciones. Por ejemplo, puede proporcionar una manera de comprobar las condiciones previas antes de llamar a un miembro para que los usuarios puedan escribir código que no produzca excepciones.

 El miembro que se usa para comprobar las condiciones previas de otro miembro a menudo se conoce como evaluador y el miembro que realmente realiza el trabajo se denomina doer.

 Hay casos en los que el patrón de Tester-Doer puede tener una sobrecarga de rendimiento inaceptable. En tales casos, se debe tener en cuenta el patrón de Try-Parse, denominado " [excepciones y rendimiento](exceptions-and-performance.md) " para obtener más información.

 ✔️ Tenga en cuenta las implicaciones de rendimiento de producir excepciones. Las tarifas de inicio por encima de 100 por segundo suelen afectar negativamente al rendimiento de la mayoría de las aplicaciones.

 ✔️ documentar todas las excepciones producidas por los miembros a los que se puede llamar públicamente debido a una infracción del contrato de miembros (en lugar de un error del sistema) y tratarlas como parte del contrato.

 Las excepciones que forman parte del contrato no deben cambiar de una versión a la siguiente (es decir, el tipo de excepción no debe cambiar y no se deben agregar nuevas excepciones).

 ❌ NO tiene miembros públicos que puedan iniciarse o no en función de alguna opción.

 ❌ NO tiene miembros públicos que devuelvan excepciones como el valor devuelto o un `out` parámetro.

 Si se devuelven excepciones desde API públicas en lugar de generarlas, se desaprovechan muchas de las ventajas de los informes de errores basados en excepciones.

 ✔️ CONSIDERE el uso de métodos del generador de excepciones.

 Es habitual producir la misma excepción desde distintos lugares. Para evitar la saturación del código, use métodos auxiliares que creen excepciones e inicialicen sus propiedades.

 Además, los miembros que inician excepciones no se insertan en línea. Mover la instrucción throw dentro del generador podría permitir que el miembro esté insertado.

 ❌ NO inicie excepciones desde bloques de filtro de excepciones.

 Cuando un filtro de excepción genera una excepción, el CLR detecta la excepción y el filtro devuelve false. Este comportamiento no se distingue del filtro que se ejecuta y devuelve false explícitamente y, por tanto, es muy difícil de depurar.

 ❌ Evite iniciar explícitamente excepciones de bloques Finally. Las excepciones iniciadas implícitamente que resultan de llamar a métodos que inician son aceptables.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de diseño de excepciones](exceptions.md)
