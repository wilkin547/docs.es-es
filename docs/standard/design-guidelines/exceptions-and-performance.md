---
title: Excepciones y rendimiento
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d664b7b61394bd9bfe6d0abd7130f9f0191e7a03
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083551"
---
# <a name="exceptions-and-performance"></a>Excepciones y rendimiento
Una preocupación comunes relacionados con las excepciones es que si las excepciones se utilizan para el código que habitualmente se produce un error, el rendimiento de la implementación será aceptable. Esto es una preocupación válida. Cuando un miembro produce una excepción, su rendimiento puede ser órdenes de magnitud más lentas. Sin embargo, es posible lograr un buen rendimiento al estrictamente siguiendo las instrucciones de la excepción que no permitir el uso de códigos de error. Dos patrones descritos en esta sección sugieren formas para hacer esto.  
  
 **X DO NOT** usar códigos de error debido a problemas que las excepciones pueden afectar negativamente al rendimiento.  
  
 Para mejorar el rendimiento, es posible usar Tester-Doer (modelo) o el patrón de Try Parse, se describe en las dos secciones siguientes.  
  
## <a name="tester-doer-pattern"></a>Tester-Doer (modelo)  
 A veces se puede mejorar el rendimiento de un miembro de inicio de excepción dividiendo el miembro en dos. Echemos un vistazo a la <xref:System.Collections.Generic.ICollection%601.Add%2A> método de la <xref:System.Collections.Generic.ICollection%601> interfaz.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 El método `Add` se produce si la colección es de solo lectura. Esto puede ser un problema de rendimiento en escenarios donde se espera que la llamada al método producirá un error con frecuencia. Una de las formas de mitigar el problema es comprobar si la colección es de escritura antes de intentar agregar un valor.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como la herramienta de comprobación. El miembro que se usa para realizar una operación potencialmente produce, la `Add` método en nuestro ejemplo, se conoce como parte de la acción.  
  
 **✓ CONSIDER** el patrón de acción de la herramienta de comprobación para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.  
  
## <a name="try-parse-pattern"></a>Patrón de try Parse  
 Para las API extremadamente sensibles al rendimiento, se debe usar un patrón aún más rápido que el patrón de Tester-Doer descrito en la sección anterior. El patrón se llama para ajustar el nombre de miembro para realizar una prueba bien definida caso una parte de la semántica de miembro. Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si el análisis de una cadena se produce un error. También define correspondiente <xref:System.DateTime.TryParse%2A> método que intenta analizar, pero devuelve false si el análisis es correcta y devuelve el resultado de una correcta con análisis un `out` parámetro.  
  
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
  
 Al utilizar este patrón, es importante definir la funcionalidad de try en términos estrictos. Si el miembro falla por alguna razón distinta try bien definida, el miembro todavía debe producir una excepción correspondiente.  
  
 **✓ CONSIDER** el patrón de Try-análisis para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.  
  
 **✓ DO** usar el prefijo "Try" y un valor booleano de tipo de valor devuelto para métodos de implementar este patrón.  
  
 **✓ DO** proporcionan un miembro que inicie excepciones para cada miembro utilizando el modelo de análisis de Try.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)
