---
title: "Excepciones y rendimiento | Microsoft Docs"
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
  - "Tester-doer (modelo)"
  - "TryParse (patrón)"
  - "excepciones, iniciar"
  - "excepciones, rendimiento"
  - "producir excepciones, rendimiento"
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Excepciones y rendimiento
Una preocupación común relacionados con las excepciones es que si las excepciones se utilizan para el código que produce errores repetidamente, el rendimiento de la implementación será aceptable. Se trata de una preocupación válida. Cuando un miembro produce una excepción, su rendimiento puede ser órdenes de magnitud más lento. Sin embargo, es posible lograr un buen rendimiento mientras estrictamente siguiendo las directrices de excepción que no permitir el uso de códigos de error. Dos modelos descritos en esta sección sugieren maneras de hacerlo.  
  
 **X no** usar códigos de error por motivos de que las excepciones podrían afectar negativamente al rendimiento.  
  
 Para mejorar el rendimiento, es posible utilizar el patrón Tester\-Doer o el modelo de análisis Try, se describen en las dos secciones siguientes.  
  
## Tester\-Doer \(modelo\)  
 A veces puede mejorarse el rendimiento de un miembro de inicio de excepción dividiendo el miembro en dos. Echemos un vistazo a la <xref:System.Collections.Generic.ICollection%601.Add%2A> el método de la <xref:System.Collections.Generic.ICollection%601> interfaz.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 El método `Add` se produce si la colección es de sólo lectura. Esto puede ser un problema de rendimiento en escenarios donde se espera que la llamada al método producirá un error con frecuencia. Una de las formas de mitigar el problema es probar si la colección es de escritura antes de intentar agregar un valor.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como el personal de pruebas. El miembro que se utiliza para realizar una operación potencialmente produce, la `Add` método en nuestro ejemplo, se conoce como la acción.  
  
 **✓, considere la posibilidad de** el patrón Tester\-Doer para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.  
  
## Patrón de try\-análisis  
 Para las API de rendimiento es sumamente importante, debe utilizarse un patrón incluso más rápido que el patrón Tester\-Doer descrito en la sección anterior. El patrón se llama para ajustar el nombre del miembro para realizar una prueba diferenciada caso una parte de la semántica del miembro. Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si el análisis de una cadena, se produce un error. También define correspondiente <xref:System.DateTime.TryParse%2A> método que intenta analizar, pero devuelve false si el análisis no es satisfactoria y devuelve el resultado de una correcta mediante análisis un `out` parámetro.  
  
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
  
 Al utilizar este patrón, es importante definir la funcionalidad de try en términos estrictos. Si el miembro falla por algún motivo que no sea el intento bien definido, el miembro todavía debe producir una excepción correspondiente.  
  
 **✓, considere la posibilidad de** el modelo de análisis Try para los miembros que pueden iniciar excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.  
  
 **✓ hacer** usar el prefijo "Try" y un valor booleano de tipo de valor devuelto para métodos de implementar este patrón.  
  
 **✓ hacer** proporcionan un miembro que inicie excepciones para cada miembro utilizando el modelo de análisis de Try.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md)