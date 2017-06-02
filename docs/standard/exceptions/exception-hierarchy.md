---
title: "Jerarqu&#237;a de excepciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "excepciones, tipos"
  - "tiempo de ejecución, excepciones"
  - "excepciones base"
  - "ApplicationException (clase)"
  - "Common language runtime, excepciones"
  - "Interoperabilidad COM, excepciones"
  - "excepciones, jerarquías"
ms.assetid: f7d68675-be06-40fb-a555-05f0c5a6f66b
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# Jerarqu&#237;a de excepciones
Hay dos tipos de excepciones: las excepciones generadas por un programa en ejecución y las excepciones generadas por Common Language Runtime. Más aún, existe toda una jerarquía de excepciones que pueden iniciar una aplicación o el motor en tiempo de ejecución.  
  
 El <xref:System.Exception?displayProperty=fullName> clase es la clase base para excepciones. Varias clases de excepciones heredan directamente de <xref:System.Exception>, incluidos <xref:System.ApplicationException> y <xref:System.SystemException>. Estas dos clases forman la base para casi todas las excepciones en tiempo de ejecución.  
  
 La mayoría de las excepciones que derivan directamente de <xref:System.Exception> agregar ninguna funcionalidad ni ningún miembro nuevo a él. Por ejemplo, el <xref:System.InvalidCastException> jerarquía de clases es como sigue:  
  
 <xref:System.Object> <xref:System.Exception> <xref:System.SystemException> <xref:System.InvalidCastException>  
  
 El tiempo de ejecución inicia la clase derivada adecuada de <xref:System.SystemException> cuando se producen errores. Estos errores son el resultado de comprobaciones de errores en tiempo de ejecución (como los errores de matriz fuera de límite) y pueden producirse durante la ejecución de cualquier método. Si está diseñando una aplicación que crea excepciones nuevas, debe derivar esas excepciones de la <xref:System.Exception> clase. No se recomienda que captura un <xref:System.SystemException>, tampoco es buena práctica de programación para producir un <xref:System.SystemException> en su aplicación.  
  
 Las excepciones más severas, las que inicia el tiempo de ejecución o en condiciones irrecuperables, incluyen <xref:System.ExecutionEngineException>, <xref:System.StackOverflowException>, y <xref:System.OutOfMemoryException>.  
  
 Las excepciones de interoperación derivan de <xref:System.SystemException> y se extiende más <xref:System.Runtime.InteropServices.ExternalException>. Por ejemplo, <xref:System.Runtime.InteropServices.COMException> es la excepción que se produce durante las operaciones de interoperabilidad COM y se deriva de <xref:System.Runtime.InteropServices.ExternalException>. <xref:System.ComponentModel.Win32Exception> y <xref:System.Runtime.InteropServices.SEHException> también derivan de <xref:System.Runtime.InteropServices.ExternalException>.  
  
## <a name="hierarchy-of-runtime-exceptions"></a>Jerarquía de las excepciones en tiempo de ejecución  
 El tiempo de ejecución tiene un conjunto base de excepciones que derivan de <xref:System.SystemException> que inicia cuando está ejecutando instrucciones individuales. En la tabla siguiente se enumeran de forma jerárquica las excepciones estándares que proporciona el tiempo de ejecución y las condiciones en que se debe crear una clase derivada.  
  
|Tipo de excepción|Tipo base|Descripción|Ejemplo|  
|--------------------|---------------|-----------------|-------------|  
|[(Excepción)](../../../docs/standard/exceptions/exception-class-and-properties.md)|<xref:System.Object>|Clase base de todas las excepciones.|Ninguno (utilice una clase derivada de esta excepción).|  
|<xref:System.SystemException>|<xref:System.Exception>|Clase base de todos los errores generados en tiempo de ejecución.|Ninguno (utilice una clase derivada de esta excepción).|  
|<xref:System.IndexOutOfRangeException>|<xref:System.SystemException>|El tiempo de ejecución la genera solo cuando una matriz no está correctamente indexada.|La indexación de una matriz fuera de su intervalo válido:<br /><br /> `var i = arr[arr.Length + 1];`<br /><br /> `Dim i = arr(arr.Length + 1)`|  
|<xref:System.NullReferenceException>|<xref:System.SystemException>|El tiempo de ejecución la genera solo cuando se hace referencia a un objeto null.|`object o = null; string s = o.ToString();`<br /><br /> `Dim o As Object = Nothing Dim s As String = o.ToString()`|  
|<xref:System.AccessViolationException>|<xref:System.SystemException>|El tiempo de ejecución la genera solo cuando se accede a memoria no válida.|Se produce cuando se interopera con código no administrado o código administrado no seguro y se usa un puntero no válido.|  
|<xref:System.InvalidOperationException>|<xref:System.SystemException>|Los métodos la generan si se produce un estado no válido.|Llamar el enumerador `GetNext` método después de quitar un elemento de la colección subyacente.|  
|<xref:System.ArgumentException>|<xref:System.SystemException>|Clase base de todas las excepciones de argumento.|Ninguno (utilice una clase derivada de esta excepción).|  
|<xref:System.ArgumentNullException>|<xref:System.ArgumentException>|Los métodos que no permiten que un argumento sea null la generan.|`String s = null; int i = "Calculate".IndexOf(s);`<br /><br /> `Dim s As String = Nothing Dim i As Integer = "Calculate".IndexOf(s)`|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.ArgumentException>|Los métodos que comprueban que los argumentos se encuentran en un intervalo determinado la generan.|`String s = "string"; s = s.Substring(s.Length + 1);`<br /><br /> `Dim s As String = "string" s = s.Substring(s.Length + 1)`|  
|<xref:System.Runtime.InteropServices.ExternalException>|<xref:System.SystemException>|Clase base de las excepciones que se producen o van dirigidas a entornos fuera del tiempo de ejecución.|Ninguno (utilice una clase derivada de esta excepción).|  
|<xref:System.Runtime.InteropServices.COMException>|<xref:System.Runtime.InteropServices.ExternalException>|Excepción que encapsula información de COM HRESULT.|Se utiliza en la interoperabilidad COM.|  
|<xref:System.Runtime.InteropServices.SEHException>|<xref:System.Runtime.InteropServices.ExternalException>|Excepción que encapsula información de control de excepciones estructurada de Win32.|Se utiliza en interoperabilidad de código no administrado.|  
  
## <a name="see-also"></a>Vea también  
 [Clase exception y propiedades](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Procedimientos recomendados para excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Excepciones](../../../docs/standard/exceptions/index.md)