---
title: Excepciones y rendimiento
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: KrzysztofCwalina
ms.openlocfilehash: f9fe3045d8bd8b4d625c5cd49bc18574ebb740de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026437"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)
