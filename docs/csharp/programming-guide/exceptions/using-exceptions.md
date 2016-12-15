---
title: "Utilizar excepciones (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "control de excepciones [C#], acerca del control de excepciones"
  - "excepciones [C#], acerca de excepciones"
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar excepciones (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En el lenguaje C\#, los errores del programa se difunden en tiempo de ejecución a través del programa mediante un mecanismo denominado excepciones.  Las excepciones se producen cuando el código encuentra un error y se detectan mediante el código que puede corregir el error.  Las excepciones se pueden producir mediante el Common Language Runtime \(CLR\) de .NET Framework o mediante código de un programa.  Una vez que se produce una excepción, ésta se difunde a la pila de llamadas hasta que se encuentra una instrucción `catch` para la excepción.  Las excepciones no detectadas se identifican a través de un controlador de excepciones genérico proporcionado por el sistema que muestra un cuadro de diálogo.  
  
 Las clases derivadas de <xref:System.Exception> representan estas excepciones.  Esta clase identifica el tipo de excepción y contiene las propiedades que albergan detalles acerca de ésta.  Producir una excepción implica crear una instancia de una clase derivada de la excepción, configurar opcionalmente las propiedades de la excepción y, a continuación, iniciar el objeto con la palabra clave `throw`.  Por ejemplo:  
  
 [!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]  
  
 Después de que se produzca una excepción, el motor en tiempo de ejecución comprueba la instrucción actual para ver si está dentro de un bloque `try`.  Si es así, se comprueba cualquier bloque `catch` asociado al bloque `try` para ver si puede detectar la excepción.  Los bloques `Catch` especifican generalmente los tipos de excepción; si el tipo del bloque `catch` es el mismo tipo de la excepción o de una clase base de la excepción, el bloque `catch` puede controlar el método.  Por ejemplo:  
  
 [!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]  
  
 Si la instrucción que produce una excepción no está dentro de un bloque `try` o el bloque `try` que la encierra no tiene un bloque `catch` coincidente, el motor en tiempo de ejecución comprueba el método de llamada a una instrucción `try` y a los bloques `catch`.  El motor en ejecución continúa hasta la pila de llamadas, en búsqueda de un bloque `catch` compatible.  Después de encontrar y ejecutar el bloque `catch`, el control se pasa a la siguiente instrucción después de ese bloque `catch`.  
  
 Una instrucción `try` puede contener más de un bloque `catch`.  Se ejecuta la primera instrucción `catch` que puede controlar la excepción; cualquier instrucción `catch` posterior, aun cuando sea compatible, se omite.  Por consiguiente, los bloques catch siempre deberían ordenarse de más específico \(o más derivado\) a menos específico.  Por ejemplo:  
  
 [!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]  
  
 Antes de que se ejecute el bloque `catch`, el motor en tiempo de ejecución comprueba los bloques `finally`.  Los bloques `Finally` permiten al programador limpiar cualquier estado ambiguo que pudiera haber quedado de un bloque `try` anulado o liberar cualquier recurso externo \(como controladores de gráficos, conexiones de base de datos o secuencias de archivos\) sin esperar a que el recolector de elementos no utilizados del motor en tiempo de ejecución finalice los objetos.  Por ejemplo:  
  
 [!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]  
  
 Si `WriteByte()` produjo una excepción, el código del segundo bloque `try` que intenta abrir de nuevo el archivo produciría un error si no se llama a `file.Close()`, y el archivo permanecería bloqueado.  Debido a que los bloques `finally` se ejecutan aunque se produzca una excepción, el bloque `finally` del ejemplo anterior permite al archivo cerrarse correctamente y ayuda a evitar un error.  
  
 Si no se encuentra ningún bloque `catch` compatible en la pila de llamadas después de que se produzca una excepción, puede suceder una de estas tres cosas:  
  
-   Si la excepción está dentro de un destructor, el destructor se anula y se llama al destructor base, si existe.  
  
-   Si la pila de llamadas contiene un constructor estático o un inicializador de campo estático, se produce una <xref:System.TypeInitializationException>, con la excepción original asignada a la propiedad <xref:System.Exception.InnerException%2A> de la nueva excepción.  
  
-   Si se alcanza el comienzo del subproceso, éste finaliza.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)