---
title: "C&#243;mo: Declarar un delegado, crear instancias del mismo y utilizarlo (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "delegados [C#], declarar y crear instancias"
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Declarar un delegado, crear instancias del mismo y utilizarlo (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En C\# 1.0 y versiones posteriores, los delegados pueden declararse tal y como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 C\# 2.0 proporciona una manera más sencilla de escribir la declaración anterior, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 En C\# 2.0 y versiones posteriores, también es posible usar un método anónimo para declarar e inicializar un [delegado](../../../csharp/language-reference/keywords/delegate.md), tal y como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 En C\# 3.0 y versiones posteriores, también se pueden crear declaraciones e instancias de los delegados usando una expresión lambda, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 El siguiente ejemplo ilustra la declaración, creación de instancias y uso de un delegado.  La clase `BookDB` encapsula una base de datos de los libros de una librería.  Expone un método `ProcessPaperbackBooks`, el cual busca todos los libros en edición rústica de la base de datos y llama a un delegado para cada uno.  El tipo `delegate` que se utiliza se denomina `ProcessBookDelegate`.  La clase `Test` utiliza esta clase para imprimir los títulos y el precio medio de los libros en edición rústica.  
  
 El uso de delegados promueve una buena separación de la funcionalidad entre la base de datos de la librería y el código del programa cliente.  El código del cliente no tiene conocimiento de cómo están almacenados los libros ni de cómo busca el código de la librería de los libros en rústica.  El código de la librería no conoce qué procesamiento se realiza sobre los libros en rústica después de encontrarlos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## Programación eficaz  
  
-   Declarar un delegado.  
  
     La instrucción siguiente declara un nuevo tipo delegado.  
  
     [!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     Cada tipo delegado describe el número y tipo de los argumentos, así como el tipo del valor devuelto de los métodos que puede encapsular.  Cuando se necesita un nuevo conjunto de tipos de argumentos o de valor devuelto, se debe declarar un nuevo tipo delegado.  
  
-   Crear instancias de un delegado.  
  
     Una vez declarado un tipo delegado, debe crearse un objeto delegado y asociarlo con un determinado método.  En el ejemplo anterior, esto se hace pasando el método `PrintTitle` al método `ProcessPaperbackBooks` como en el ejemplo siguiente:  
  
     [!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     Esto crea un nuevo objeto delegado asociado con el método [estático](../../../csharp/language-reference/keywords/static.md) `Test.PrintTitle`.  De igual forma, el método no estático `AddBookToTotal` del objeto `totaller` se pasa como en el ejemplo siguiente:  
  
     [!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     En ambos casos, este nuevo objeto delegado se pasa al método `ProcessPaperbackBooks`.  
  
     Una vez que se crea el delegado, el método con el que está asociado no cambia nunca; los objetos delegados son inmutables.  
  
-   Llamar a un delegado.  
  
     Una vez creado un objeto delegado, éste se pasa normalmente a otro código que llamará al delegado.  La llamada a un objeto delegado se realiza mediante el nombre del objeto delegado, seguido por los argumentos entre paréntesis que se pasarán al delegado.  A continuación, se muestra un ejemplo de una llamada a delegado:  
  
     [!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     Se puede llamar a un delegado de forma sincrónica, como en este ejemplo, o de forma asincrónica, utilizando los métodos `BeginInvoke` y `EndInvoke`.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)