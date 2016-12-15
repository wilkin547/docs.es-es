---
title: "Crear y producir excepciones (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "detectar excepciones [C#]"
  - "excepciones [C#], crear"
  - "excepciones [C#], iniciar"
  - "producir excepciones [C#]"
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Crear y producir excepciones (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las excepciones se utilizan para indicar que se ha producido un error mientras el programa está en ejecución.  Los objetos de excepción que describen un error se crean y, a continuación, se *producen* con la palabra clave [throw](../../../csharp/language-reference/keywords/throw.md).  El motor de ejecución busca el controlador de excepciones más compatible.  
  
 Los programadores deberían iniciar excepciones cuando se cumpla al menos una de las siguientes condiciones:  
  
-   El método no puede finalizar su funcionalidad definida.  
  
     Por ejemplo, si el parámetro de un método tiene un valor no válido:  
  
     [!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]  
  
-   Se realiza una llamada inadecuada a un objeto, basada en el estado del objeto.  
  
     Un ejemplo sería tratar de escribir en un archivo de sólo lectura.  En los casos en que el estado del objeto no permite realizar una operación, produzca una instancia de <xref:System.InvalidOperationException> o un objeto basado en una derivación de esta clase.  Éste es un ejemplo de un método que produce un objeto <xref:System.InvalidOperationException>:  
  
     [!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]  
  
-   Cuando un argumento para un método provoca una excepción.  
  
     En este caso, se debería detectar una excepción original y se debería crear una instancia de <xref:System.ArgumentException>.  La excepción original se debería pasar al constructor de <xref:System.ArgumentException> como el parámetro <xref:System.Exception.InnerException%2A>:  
  
     [!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]  
  
 Las excepciones contienen una propiedad denominada <xref:System.Exception.StackTrace%2A>.  Esta cadena contiene el nombre de los métodos incluidos en la pila actual de llamadas, junto con el nombre del archivo y el número de línea donde se produjo la excepción para cada método.  Common Language Runtime \(CRL\) crea automáticamente un objeto <xref:System.Exception.StackTrace%2A> desde el punto de la instrucción `throw`, de modo que las excepciones se deben iniciar desde el punto donde debe comenzar el seguimiento de la pila.  
  
 Todas las excepciones contienen una propiedad denominada <xref:System.Exception.Message%2A>.  Esta cadena debería contener el motivo de la excepción.  Tenga en cuenta que no se debe colocar información confidencial de seguridad en el texto del mensaje.  Además de <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contiene una propiedad denominada <xref:System.ArgumentException.ParamName%2A> cuyo valor debe ser el nombre del argumento que provocó que se iniciara la excepción.  En el caso de un establecedor de propiedades, <xref:System.ArgumentException.ParamName%2A> se debería establecer en `value`.  
  
 Los miembros de métodos públicos y protegidos deberían producir excepciones cada vez que no pueden finalizar sus funciones deseadas.  La clase de excepción producida debería ser la excepción más concreta disponible que se ajuste a las condiciones del error.  Estas excepciones se deberían documentar como parte de la funcionalidad de la clase, y las clases derivadas o actualizaciones de la clase original deberían mantener el mismo comportamiento a efectos de compatibilidad con versiones anteriores.  
  
## Cosas que hay que evitar al producir excepciones  
 La siguiente lista identifica las prácticas que hay que evitar a la hora de producir excepciones:  
  
-   Las excepciones no se deberían utilizar para cambiar el flujo de un programa en una ejecución normal.  Las excepciones sólo se deberían utilizar para comunicar y tratar errores.  
  
-   Las excepciones no se deben devolver como un valor o parámetro en lugar de iniciarse.  
  
-   No inicie intencionadamente <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> o <xref:System.IndexOutOfRangeException?displayProperty=fullName> desde el propio código fuente.  
  
-   No cree excepciones que se pueden iniciar en modo de depuración pero no en modo de versión de lanzamiento.  Para identificar errores en tiempo de ejecución durante la fase de desarrollo, use en su lugar el método Debug Assert.  
  
## Definir clases de excepción  
 Los programas pueden iniciar una clase de excepción predefinida en el espacio de nombres <xref:System> \(excepto donde se indicó anteriormente\) o crear sus propias clases de excepción mediante derivación de <xref:System.Exception>.  Las clases derivadas deberían definir al menos cuatro constructores: un constructor predeterminado, uno que establezca la propiedad message y otro que establezca las propiedades <xref:System.Exception.Message%2A> y <xref:System.Exception.InnerException%2A>.  El cuarto constructor se utiliza para serializar la excepción.  Las nuevas clases de excepción deberían ser serializables.  Por ejemplo:  
  
 [!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]  
  
 Las nuevas propiedades sólo se deberían agregar a la clase de excepción cuando los datos que proporcionan son útiles para resolver la excepción.  Si a la clase de excepción derivada se agregan nuevas propiedades, `ToString()` se debería reemplazar para devolver la información agregada.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Jerarquía de excepciones](../Topic/Exception%20Hierarchy.md)   
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)