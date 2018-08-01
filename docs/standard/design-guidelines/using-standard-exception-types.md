---
title: Usar tipos de excepciones estándar
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81e4047c171e3a58f335821d64390432524b25df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574600"
---
# <a name="using-standard-exception-types"></a>Usar tipos de excepciones estándar
Esta sección describe las excepciones estándar que proporciona el marco de trabajo y los detalles de su uso. La lista no es exhaustiva. Consulte la documentación de referencia de .NET Framework para el uso de otros tipos de excepción de Framework.  
  
## <a name="exception-and-systemexception"></a>Exception y SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** catch `System.Exception` o `System.SystemException` en el código de framework, a menos que vaya a producir.  
  
 **X AVOID** detectar `System.Exception` o `System.SystemException`, excepto en los controladores de excepciones de nivel superior.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw o derivar de <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** producir una <xref:System.InvalidOperationException> si el objeto está en un estado inadecuado.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException y ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos incorrectos a un miembro. Preferir el tipo de excepción más derivado, si procede.  
  
 **✓ DO** establecer el `ParamName` propiedad al producir una de las subclases de `ArgumentException`.  
  
 Esta propiedad representa el nombre del parámetro que provocó la excepción. Tenga en cuenta que la propiedad puede establecerse utilizando una de las sobrecargas del constructor.  
  
 **✓ DO** usar `value` para el nombre del parámetro de valor implícito de establecedores de propiedades.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>Excepción NullReferenceException, IndexOutOfRangeException y AccessViolationException  
 **X DO NOT** permitir que las API invocables públicamente explícita o implícitamente produzca <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>. Estas excepciones son reservadas y producida por el motor de ejecución y en que la mayoría de casos indican un error.  
  
 Realice la comprobación para evitar estas excepciones de argumento. Al iniciar estas excepciones expone los detalles de implementación del método que puede cambiar con el tiempo.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** iniciar explícitamente <xref:System.StackOverflowException>. Debe producirse explícitamente la excepción solo por CLR.  
  
 **X DO NOT** catch `StackOverflowException`.  
  
 Es prácticamente imposible escribir código administrado que siga siendo coherente en presencia de desbordamientos de pila arbitrario. Las partes no administradas de CLR permanezcan coherentes mediante sondeos para mover la pila se desborda en lugares bien definidos en lugar de realizar la copia de los desbordamientos de pila arbitrario.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** iniciar explícitamente <xref:System.OutOfMemoryException>. Esta excepción es que se produzca únicamente por la infraestructura CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException y SEHException, ExecutionEngineException  
 **X DO NOT** iniciar explícitamente <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, y <xref:System.Runtime.InteropServices.SEHException>. Estas excepciones son que se produzca únicamente por la infraestructura CLR.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md)
