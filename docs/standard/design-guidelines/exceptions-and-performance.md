---
title: Excepciones y rendimiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c2d7cfcb228c492d2adbe614d0ed88a3b02bb68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exceptions-and-performance"></a>Excepciones y rendimiento
Una preocupación comunes relacionados con las excepciones es que si las excepciones se utilizan para el código que produce errores repetidamente, el rendimiento de la implementación es inaceptable. Se trata de una preocupación válida. Cuando un miembro produce una excepción, su rendimiento puede ser órdenes de magnitud más lento. Sin embargo, es posible lograr un buen rendimiento al estrictamente siguiendo las directrices de excepción que no permitir el uso de códigos de error. Dos patrones que se describen en esta sección ofrecen sugerencias para hacer esto.  
  
 **X DO NOT** usar códigos de error debido a problemas que las excepciones pueden afectar negativamente al rendimiento.  
  
 Para mejorar el rendimiento, es posible utilizar el patrón de acción de la herramienta de comprobación o el patrón de Try-análisis, se describe en las dos secciones siguientes.  
  
## <a name="tester-doer-pattern"></a>Patrón de acción de la herramienta de comprobación  
 A veces se puede mejorar el rendimiento de un miembro que inicie excepciones dividiendo el miembro en dos. Echemos un vistazo a la <xref:System.Collections.Generic.ICollection%601.Add%2A> método de la <xref:System.Collections.Generic.ICollection%601> interfaz.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 El método `Add` produce si la colección es de solo lectura. Esto puede ser un problema de rendimiento en escenarios donde se espera que la llamada al método producirá un error con frecuencia. Uno de los métodos para mitigar el problema es probar si la colección es de escritura antes de intentar agregar un valor.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como la herramienta de comprobación. El miembro que se usa para realizar una operación potencialmente produce, la `Add` método en nuestro ejemplo, se conoce como la acción.  
  
 **✓ Considere la posibilidad de** el patrón de acción de la herramienta de comprobación para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.  
  
## <a name="try-parse-pattern"></a>Patrón de try-análisis  
 Para las API de rendimiento es sumamente importante, debe utilizarse un patrón aun más rápido que el patrón de acción de la herramienta de comprobación se describe en la sección anterior. El patrón de las llamadas para ajustar el nombre del miembro para realizar una prueba bien definida caso una parte de la semántica de miembro. Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si el análisis de una cadena se produce un error. También define un correspondiente <xref:System.DateTime.TryParse%2A> método que intenta analizar, pero devuelve false si el análisis es incorrecto y devuelve el resultado de una correcta con análisis un `out` parámetro.  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 Al utilizar este patrón, es importante definir la funcionalidad de try en términos estrictos. Si se produce un error en el miembro por cualquier razón distinta a la instrucción try bien definida, el miembro todavía debe producir una excepción correspondiente.  
  
 **✓ Considere la posibilidad de** el patrón de Try-análisis para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.  
  
 **✓ HACER** usar el prefijo "Try" y un valor booleano de tipo de valor devuelto para métodos de implementar este patrón.  
  
 **✓ HACER** proporcionan un miembro que inicie excepciones para cada miembro utilizando el modelo de análisis de Try.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md)
