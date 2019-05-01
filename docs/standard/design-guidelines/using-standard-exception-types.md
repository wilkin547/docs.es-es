---
title: Usar tipos de excepciones estándar
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: KrzysztofCwalina
ms.openlocfilehash: b947c7cce057c060b1ab5054d1227f5703ccbf89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026346"
---
# <a name="using-standard-exception-types"></a>Usar tipos de excepciones estándar
Esta sección describen las excepciones estándar proporcionadas por el marco de trabajo y los detalles de su uso. La lista no es exhaustiva. Consulte la documentación de referencia de .NET Framework para el uso de otros tipos de excepción de Framework.  
  
## <a name="exception-and-systemexception"></a>Excepción y SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** catch `System.Exception` o `System.SystemException` en el código de framework, a menos que vaya a producir.  
  
 **X AVOID** detectar `System.Exception` o `System.SystemException`, excepto en los controladores de excepciones de nivel superior.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw o derivar de <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** producir una <xref:System.InvalidOperationException> si el objeto está en un estado inadecuado.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException y ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos incorrectos a un miembro. Prefiere el tipo más derivado excepción, si procede.  
  
 **✓ DO** establecer el `ParamName` propiedad al producir una de las subclases de `ArgumentException`.  
  
 Esta propiedad representa el nombre del parámetro que provocó la excepción que se produzca. Tenga en cuenta que la propiedad puede establecerse mediante una de las sobrecargas del constructor.  
  
 **✓ DO** usar `value` para el nombre del parámetro de valor implícito de establecedores de propiedades.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>Excepción NullReferenceException, IndexOutOfRangeException y AccessViolationException  
 **X DO NOT** permitir que las API invocables públicamente explícita o implícitamente produzca <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>. Estas excepciones son reservadas y producida por el motor de ejecución y en que la mayoría de los casos indican un error.  
  
 Realizar comprobaciones para evitar estas excepciones de argumento. Estas excepciones exponen los detalles de implementación del método que se pueden cambiar con el tiempo.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** iniciar explícitamente <xref:System.StackOverflowException>. La excepción debe producirse explícitamente sólo por CLR.  
  
 **X DO NOT** catch `StackOverflowException`.  
  
 Es casi imposible escribir código administrado que siga siendo coherente en el caso de los desbordamientos de pila arbitrario. Las partes no administradas de CLR siguen siendo coherentes mediante sondeos para mover los desbordamientos de pila en lugares bien definidos en lugar de reversión de los desbordamientos de pila arbitrario.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** iniciar explícitamente <xref:System.OutOfMemoryException>. Esta excepción es que se produzca solo por la infraestructura de CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException SEHException y ExecutionEngineException  
 **X DO NOT** iniciar explícitamente <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, y <xref:System.Runtime.InteropServices.SEHException>. Estas excepciones son que se produzca solo por la infraestructura de CLR.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)
