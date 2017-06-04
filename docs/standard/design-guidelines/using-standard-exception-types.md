---
title: "Uso de tipos de excepci&#243;n est&#225;ndar | Microsoft Docs"
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
  - "producir excepciones, tipos estándar"
  - "detectar excepciones"
  - "excepciones, detectar"
  - "excepciones, iniciar"
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Uso de tipos de excepci&#243;n est&#225;ndar
Esta sección describe las excepciones estándar que proporciona el marco de trabajo y los detalles de su uso. La lista no es exhaustiva. Consulte la documentación de referencia de .NET Framework para el uso de otros tipos de excepción de Framework.  
  
## Exception y SystemException  
 **X no** throw <xref:System.Exception?displayProperty=fullName> o <xref:System.SystemException?displayProperty=fullName>.  
  
 **X no** catch `System.Exception` o `System.SystemException` en el código de framework, a menos que vaya a producir.  
  
 **Evitar X** detectar `System.Exception` o `System.SystemException`, salvo en los controladores de excepciones de nivel superior.  
  
## ApplicationException  
 **X no** inicie o derive de <xref:System.ApplicationException>.  
  
## InvalidOperationException  
 **✓ hacer** producir una <xref:System.InvalidOperationException> Si el objeto está en un estado inadecuado.  
  
## ArgumentException, ArgumentNullException y ArgumentOutOfRangeException  
 **✓ hacer** throw <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos incorrectos a un miembro. Preferir el tipo de excepción más derivado, si procede.  
  
 **✓ hacer** establecer el `ParamName` propiedad cuando se produce una de las subclases de `ArgumentException`.  
  
 Esta propiedad representa el nombre del parámetro que provocó la excepción. Tenga en cuenta que la propiedad puede establecerse utilizando una de las sobrecargas del constructor.  
  
 **✓ hacer** usar `value` para el nombre del parámetro de valor implícito de establecedores de propiedad.  
  
## NullReferenceException IndexOutOfRangeException y AccessViolationException  
 **X no** permiten que las API invocables públicamente explícita o implícita <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>. Estas excepciones están reservadas y producida por el motor de ejecución y suele indica un error en.  
  
 Realizar comprobaciones para evitar estas excepciones. Estas excepciones exponen los detalles de implementación de un método que puede cambiar con el tiempo.  
  
## StackOverflowException  
 **X no** iniciar explícitamente <xref:System.StackOverflowException>. La excepción debe producirse explícitamente sólo por CLR.  
  
 **X no** catch `StackOverflowException`.  
  
 Es casi imposible escribir código administrado que siga siendo coherente en presencia de desbordamientos de pila arbitrario. Las partes no administradas de CLR siguen siendo coherentes mediante sondeos para mover los desbordamientos de pila en lugares bien definidos en lugar de reversión de desbordamientos de pila arbitrario.  
  
## OutOfMemoryException  
 **X no** iniciar explícitamente <xref:System.OutOfMemoryException>. Esta excepción es que se produzca únicamente por la infraestructura de CLR.  
  
## ExecutionEngineException, ComException y SEHException  
 **X no** iniciar explícitamente <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, y <xref:System.Runtime.InteropServices.SEHException>. Estas excepciones son se produce únicamente por la infraestructura de CLR.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md)