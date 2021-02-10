---
description: 'Más información acerca de: Generación de excepciones'
title: Generación de excepciones
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: b1cf7a4eecc32a9f76ea06c47dd6c16d3afe5470
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642141"
---
# <a name="exception-throwing"></a>Generación de excepciones

Las instrucciones de generación de excepciones descritas en esta sección precisan que definamos bien el significado de "error de ejecución". El error de ejecución se produce siempre que un miembro no puede hacer lo que se le diseñó (indicado en el propio nombre del miembro). Por ejemplo, si el método `OpenFile` no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.

 La mayoría de los desarrolladores se han familiarizado con el uso de las excepciones de errores de uso, como la división por cero o las referencias nulas. En el marco, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.

 ❌ NO devuelva códigos de error.

 Las excepciones son el medio principal para informar de errores en marcos.

 ✔️ Informe de los errores de ejecución generando excepciones.

 ✔️ Recomendamos terminar el proceso llamando a `System.Environment.FailFast` (característica de .NET Framework 2.0) en lugar de generar una excepción si el código encuentra una situación en la que no es seguro ejecutarse posteriormente.

 ❌ NO utilice excepciones para el flujo de control normal, si es posible.

 A excepción de los errores del sistema y las operaciones con posibles condiciones de carrera, los diseñadores de marcos deben diseñar las API para que los usuarios puedan escribir código que no genere excepciones. Por ejemplo, puede proporcionar una manera de comprobar las condiciones previas antes de llamar a un miembro para que los usuarios puedan escribir código que no genere excepciones.

 El miembro que se usa para comprobar las condiciones previas de otro miembro suele denominarse "evaluador" y el miembro que realmente realiza el trabajo se llama "doer".

 Hay casos en los que el patrón tester-doer puede tener una sobrecarga de rendimiento inaceptable. En estos casos, se debe tener en cuenta el patrón llamado "try-parse" (consulte [Excepciones y rendimiento](exceptions-and-performance.md) para obtener más información).

 ✔️ Tenga en cuenta las implicaciones de rendimiento que tiene generar excepciones. Las tasas de generación de excepciones que estén por encima de 100 por segundo suelen afectar negativamente al rendimiento de la mayoría de las aplicaciones.

 ✔️ Documente todas las excepciones generadas por los miembros invocables públicamente debido a una infracción del contrato de miembros (en lugar de un error del sistema) y considérelas como parte del contrato.

 Las excepciones que forman parte del contrato no deberían cambiar de una versión a la siguiente (es decir, el tipo de excepción no debe cambiar y no se deben agregar nuevas excepciones).

 ❌ NO tenga miembros públicos que puedan iniciarse o no en función de alguna opción.

 ❌ NO tenga miembros públicos que devuelvan excepciones como el valor devuelto o un parámetro `out`.

 Si se devuelven excepciones desde API públicas en lugar de generarlas, se desaprovechan muchas de las ventajas de los informes de errores basados en excepciones.

 ✔️ Recomendamos usar métodos del generador de excepciones.

 Es habitual generar la misma excepción desde distintos lugares. Para evitar el sobredimensionamiento del código, use métodos auxiliares que creen excepciones e inicialicen sus propiedades.

 Además, los miembros que generan excepciones no se insertan en línea. Mover la instrucción throw dentro del generador podría permitir que el miembro quede insertado.

 ❌ NO genere excepciones desde bloques de filtros de excepciones.

 Cuando un filtro de excepción genera una excepción, CLR la detecta y el filtro devuelve el valor false. Este comportamiento es idéntico al del filtro que se ejecuta y devuelve el valor false explícitamente y, por lo tanto, es muy difícil de depurar.

 ❌ EVITE generar explícitamente excepciones de bloques Finally. Se aceptan las excepciones generadas implícitamente como consecuencia de llamar a métodos que se inician.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Instrucciones de diseño de excepciones](exceptions.md)
