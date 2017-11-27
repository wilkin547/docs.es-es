---
title: "Usar tipos de excepciones estándar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 91cd9a03ad1acf61681ecfad0edb061802c4362c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-standard-exception-types"></a>Usar tipos de excepciones estándar
Esta sección describe las excepciones estándar que proporciona el marco de trabajo y los detalles de su uso. La lista no es exhaustiva. Consulte la documentación de referencia de .NET Framework para el uso de otros tipos de excepción de Framework.  
  
## <a name="exception-and-systemexception"></a>Exception y SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** catch `System.Exception` o `System.SystemException` en el código de framework, a menos que vaya a producir.  
  
 **X evitar** detectar `System.Exception` o `System.SystemException`, excepto en los controladores de excepciones de nivel superior.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw o derivar de <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ HACER** producir una <xref:System.InvalidOperationException> si el objeto está en un estado inadecuado.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException y ArgumentOutOfRangeException  
 **✓ HACER** throw <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos incorrectos a un miembro. Preferir el tipo de excepción más derivado, si procede.  
  
 **✓ HACER** establecer el `ParamName` propiedad al producir una de las subclases de `ArgumentException`.  
  
 Esta propiedad representa el nombre del parámetro que provocó la excepción. Tenga en cuenta que la propiedad puede establecerse utilizando una de las sobrecargas del constructor.  
  
 **✓ HACER** usar `value` para el nombre del parámetro de valor implícito de establecedores de propiedades.  
  
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
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md)
