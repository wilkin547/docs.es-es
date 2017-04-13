---
title: "Generaci&#243;n de excepciones | Microsoft Docs"
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
helpviewer_keywords: 
  - "excepciones, iniciar"
  - "producir excepciones explícitamente"
  - "producir excepciones, instrucciones de diseño"
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Generaci&#243;n de excepciones
Instrucciones de inicio de excepción descritos en esta sección requieren una buena definición del significado del error de ejecución. Se produce un error de ejecución cada vez que un miembro no puede hacer que estaba diseñado para hacer \(lo que el nombre de miembro implica\). Por ejemplo, si la `OpenFile` método no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.  
  
 La mayoría de los desarrolladores han vuelto cómodos utilizar excepciones para errores de uso como la división por cero o referencias nulas. En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.  
  
 **X no** devolver códigos de error.  
  
 Las excepciones son el medio principal de informes de errores en los marcos.  
  
 **✓ hacer** notificar errores de ejecución iniciando excepciones.  
  
 **✓ considere** al finalizar el proceso llamando a `System.Environment.FailFast` \(característica de .NET Framework 2.0\) en lugar de producir una excepción si el código encuentra una situación donde no es seguro para la ejecución aún más.  
  
 **X no** usar excepciones para el flujo normal de control, si es posible.  
  
 Excepto los errores del sistema y operaciones con posibles condiciones de carrera, los diseñadores de framework deberían diseñar las API para que los usuarios pueden escribir código que no inicie excepciones. Por ejemplo, puede proporcionar un mecanismo para comprobar las condiciones previas antes de llamar a un miembro, por lo que los usuarios pueden escribir código que no inicie excepciones.  
  
 El miembro que se utiliza para comprobar las condiciones previas de otro miembro se conoce a menudo como una herramienta de comprobación y el miembro que hace realmente el trabajo se denomina una acción.  
  
 Hay casos Tester\-Doer \(modelo\) puede tener una sobrecarga de rendimiento inaceptable. En tales casos, debe considerarse el patrón de análisis Try llamados \(consulte [Excepciones y rendimiento](../../../docs/standard/design-guidelines/exceptions-and-performance.md) para obtener más información\).  
  
 **✓, considere la posibilidad de** las implicaciones de rendimiento de inicio de excepciones. Throw velocidades superiores a 100 por segundo suelen afectar notablemente el rendimiento de la mayoría de las aplicaciones.  
  
 **✓ hacer** documento todas las excepciones iniciadas por miembros invocables públicamente debido a una infracción del miembro de contrato \(en lugar de un error del sistema\) y tratan como parte de su contrato.  
  
 Las excepciones que forman parte del contrato no deberían cambiar de una versión a la siguiente \(es decir, no debe cambiar el tipo de excepción y no se deben agregar nuevas excepciones\).  
  
 **X no** tener miembros públicos que pueden bien throw o no en función de alguna opción.  
  
 **X no** tiene miembros públicos que devuelven excepciones como el valor devuelto o un `out` parámetro.  
  
 Devolver las excepciones de las API públicas en lugar de producir ellos frustra muchas de las ventajas de informes de errores basado en excepciones.  
  
 **✓, considere la posibilidad de** mediante métodos de generador de excepciones.  
  
 Es común para que se produzca la misma excepción desde distintos lugares. Para evitar la cantidad de código, use métodos auxiliares que crean excepciones e inicializan sus propiedades.  
  
 Además, los miembros que producen excepciones no obtienen entre líneas. Mover la instrucción throw en el generador puede permitir que el miembro se inserte.  
  
 **X no** generar excepciones desde bloques de filtro de excepción.  
  
 Cuando un filtro de excepciones provoca una excepción, la excepción es detectada por el CLR y el filtro devuelve false. Este comportamiento es indistinguible desde que el filtro se ejecuta y devuelve false explícitamente y por lo tanto, es muy difícil de depurar.  
  
 **Evitar X** iniciar explícitamente excepciones desde bloques finally. Las excepciones iniciadas implícitamente resultantes de llamar a los métodos que inician son aceptables.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md)