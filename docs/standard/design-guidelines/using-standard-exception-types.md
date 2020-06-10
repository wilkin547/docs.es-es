---
title: Usar tipos de excepciones estándar
description: Lea acerca de los tipos de excepción estándar en .NET. Obtenga información sobre SystemException, ApplicationException, ArgumentException, COMException, etc.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: f95529eabd87d9ec7c379b9f790e039e1192ac53
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84663062"
---
# <a name="using-standard-exception-types"></a>Usar tipos de excepciones estándar
En esta sección se describen las excepciones estándar proporcionadas por el marco de trabajo y los detalles de su uso. La lista no es exhaustiva. Consulte la documentación de referencia de .NET Framework para ver el uso de otros tipos de excepción de marco de trabajo.

## <a name="exception-and-systemexception"></a>Excepción y SystemException
 ❌NO Throw <xref:System.Exception?displayProperty=nameWithType> ni <xref:System.SystemException?displayProperty=nameWithType> .

 ❌NO `System.Exception` `System.SystemException` se debe detectar ni en el código del marco, a menos que se pretenda volver a producir.

 ❌Evite detectar `System.Exception` o `System.SystemException` , excepto en los controladores de excepciones de nivel superior.

## <a name="applicationexception"></a>ApplicationException
 ❌NO inicie ni derive de <xref:System.ApplicationException> .

## <a name="invalidoperationexception"></a>InvalidOperationException
 ✔️ iniciar una excepción <xref:System.InvalidOperationException> si el objeto está en un estado inadecuado.

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException y ArgumentOutOfRangeException
 ✔️ iniciar <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos no válidos a un miembro. Prefiere el tipo de excepción más derivado, si procede.

 ✔️ establecer la `ParamName` propiedad al iniciar una de las subclases de `ArgumentException` .

 Esta propiedad representa el nombre del parámetro que provocó que se produjera la excepción. Tenga en cuenta que la propiedad se puede establecer mediante una de las sobrecargas del constructor.

 ✔️ usar `value` para el nombre del parámetro de valor implícito de los establecedores de propiedad.

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException y AccessViolationException
 ❌No permita que las API a las que se puede llamar públicamente inicien, o de forma explícita o implícita <xref:System.NullReferenceException> <xref:System.AccessViolationException> <xref:System.IndexOutOfRangeException> . Estas excepciones están reservadas y iniciadas por el motor de ejecución y, en la mayoría de los casos, indican un error.

 Realice una comprobación de argumentos para evitar producir estas excepciones. Producir estas excepciones expone los detalles de implementación del método que pueden cambiar con el tiempo.

## <a name="stackoverflowexception"></a>StackOverflowException
 ❌NO inicie explícitamente <xref:System.StackOverflowException> . La excepción solo debe iniciarse explícitamente en CLR.

 ❌NO se detectan `StackOverflowException` .

 Es casi imposible escribir código administrado que permanezca coherente en la presencia de desbordamientos de pila arbitrarios. Las partes no administradas de CLR siguen siendo coherentes mediante el uso de sondeos para trasladar desbordamientos de pila a lugares bien definidos en lugar de deshacer la copia de seguridad desde desbordamientos de pila arbitrarios.

## <a name="outofmemoryexception"></a>OutOfMemoryException
 ❌NO inicie explícitamente <xref:System.OutOfMemoryException> . Esta excepción solo la debe iniciar la infraestructura de CLR.

## <a name="comexception-sehexception-and-executionengineexception"></a>COMException, SEHException y ExecutionEngineException
 ❌NO inicie explícitamente <xref:System.Runtime.InteropServices.COMException> , <xref:System.ExecutionEngineException> y <xref:System.Runtime.InteropServices.SEHException> . Estas excepciones solo se producirán en la infraestructura de CLR.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de diseño de excepciones](exceptions.md)
