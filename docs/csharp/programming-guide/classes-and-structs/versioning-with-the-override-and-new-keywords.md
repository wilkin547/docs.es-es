---
title: "Control de versiones con las palabras clave Override y New (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, override y new"
  - "lenguaje C#, control de versiones"
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# Control de versiones con las palabras clave Override y New (Gu&#237;a de programaci&#243;n de C#)
El lenguaje C\# está diseñado de modo que las versiones entre las clases [base](../../../csharp/language-reference/keywords/base.md) y derivadas de diferentes bibliotecas puedan evolucionar y mantener la compatibilidad con versiones anteriores.  Esto significa, por ejemplo, que la inserción de un nuevo miembro en una [clase](../../../csharp/language-reference/keywords/class.md) base con el mismo nombre que un miembro de una clase derivada es totalmente compatible con C\# y no lleva a un comportamiento inesperado.  También significa que una clase debe declarar explícitamente si un método va a invalidar a un método heredado o si es un nuevo método que oculta un método heredado con un nombre similar.  
  
 En C\#, las clases derivadas pueden contener métodos con el mismo nombre que los métodos de clase base.  
  
-   El método de la clase base debe definirse como [virtual](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Si el método de la clase derivada no va precedido de las palabras clave [new](../../../csharp/language-reference/keywords/new.md) u [override](../../../csharp/language-reference/keywords/override.md), el compilador emite una advertencia y el método se comporta como si la palabra clave `new` estuviera presente.  
  
-   Si el método de la clase derivada va precedido de la palabra clave `new`, el método se define como independiente del método de la clase base.  
  
-   Si el método de la clase derivada va precedido de la palabra clave `override`, los objetos de la clase derivada llamarán a ese método, no al método de la clase base.  
  
-   El método de la clase base puede llamarse desde dentro de la clase derivada con la palabra clave `base`.  
  
-   Las palabras clave `override`, `virtual` y `new` también pueden aplicarse a propiedades, indizadores y eventos.  
  
 De forma predeterminada, los métodos de C\# no son virtuales.  Si se declara un método como virtual, toda clase que hereda el método puede implementar su propia versión  Para hacer que un método sea virtual, se utiliza el modificador `virtual` en la declaración de método de la clase base.  La clase derivada puede entonces reemplazar el método base virtual mediante la palabra clave `override` u ocultar el método virtual de la clase base mediante la palabra clave `new`.  Si no se especifica la palabra clave `override` ni la palabra clave `new`, el compilador emite una advertencia y el método de la clase derivada oculta el método de la clase base.  
  
 Para demostrar esto en la práctica, supongamos por un momento que la compañía A ha creado una clase denominada `GraphicsClass` que utiliza el programa.  `GraphicsClass` se muestra a continuación:  
  
 [!code-cs[csProgGuideInheritance#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_1.cs)]  
  
 La compañía utiliza esta clase, que se utiliza para derivar clases propias, mediante la adición de un nuevo método:  
  
 [!code-cs[csProgGuideInheritance#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_2.cs)]  
  
 La aplicación se utiliza sin problemas, hasta que la compañía lanza una nueva versión de `GraphicsClass`, que se asemeja al código siguiente:  
  
 [!code-cs[csProgGuideInheritance#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_3.cs)]  
  
 La nueva versión de `GraphicsClass` contiene ahora un método denominado `DrawRectangle`.  Inicialmente, no ocurre nada.  La nueva versión aún es compatible a nivel binario con la anterior.  Todo el software que se haya implementado continuará funcionando, aunque la nueva clase esté instalada en los sistemas informáticos.  Cualquier llamada existente al método `DrawRectangle` continuará haciendo referencia a la versión, en la clase derivada.  
  
 Sin embargo, tan pronto como vuelva a compilar la aplicación con la nueva versión de `GraphicsClass`, recibirá una advertencia del compilador \(CS0108\).  Esta advertencia informa de que el usuario debe considerar cómo desea que se comporte el método `DrawRectangle` en la aplicación.  
  
 Si desea que el método invalide el nuevo método de clase base, utilice la palabra clave `override`:  
  
 [!code-cs[csProgGuideInheritance#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_4.cs)]  
  
 La palabra clave `override` se asegura de que cualquier objeto derivado de `YourDerivedGraphicsClass` utilizará la versión de clase derivada de `DrawRectangle`.  Los objetos derivados de `YourDerivedGraphicsClass` aún pueden tener acceso a la versión de clase base de `DrawRectangle` con la palabra clave base:  
  
 [!code-cs[csProgGuideInheritance#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_5.cs)]  
  
 Si no desea que el método invalide el nuevo método de clase base, tenga en cuenta las consideraciones siguientes.  Para evitar la confusión entre los dos métodos, puede cambiar el nombre del método.  Esto puede requerir mucho tiempo, llevar a errores y no resultar práctico en algunos casos.  Sin embargo, si el proyecto es relativamente pequeño, se pueden utilizar las opciones de refactorización de Visual Studio para cambiar el nombre del método.  Para obtener más información, vea [Refactoring Classes and Types \(Class Designer\)](/visual-studio/ide/refactoring-classes-and-types-class-designer).  
  
 Por otro lado, se puede evitar la advertencia mediante la palabra clave `new` en la definición de la clase derivada:  
  
 [!code-cs[csProgGuideInheritance#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_6.cs)]  
  
 Con la palabra clave `new` se indica al compilador que la definición oculta la definición contenida en la clase base.  Éste es el comportamiento predeterminado.  
  
## Selección de método y reemplazo  
 Cuando se nombra un método en una clase, el compilador de C\# selecciona el mejor método que se va a llamar si más de un método es compatible con la llamada, al igual que cuando hay dos métodos con el mismo nombre y parámetros que son compatibles con el parámetro pasado.  Los métodos siguientes serían compatibles:  
  
 [!code-cs[csProgGuideInheritance#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_7.cs)]  
  
 Cuando se llama a `DoWork` en una instancia de `Derived`, el compilador de C\# intentará primero hacer que la llamada sea compatible con las versiones de `DoWork` declaradas originalmente en `Derived`.  Los métodos de reemplazo no se consideran como declarados en una clase; son nuevas implementaciones de un método declarado en una clase base.  Sólo si el compilador de C\# no puede hacer coincidir la llamada de método con un método original de `Derived`, intentará hacer que la llamada coincida con un método de reemplazo que tenga el mismo nombre y parámetros compatibles.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_8.cs)]  
  
 Puesto que la variable `val` se puede convertir implícitamente en double, el compilador de C\# llama a `DoWork(double)` en lugar de `DoWork(int)`.  Existen dos formas para evitar esto.  En primer lugar, se debe evitar declarar nuevos métodos con el mismo nombre que los métodos virtuales.  En segundo lugar, se puede indicar al compilador de C\# que llame al método virtual haciendo que busque la lista de métodos de la clase base mediante la conversión de la instancia de `Derived` en `Base`.  Debido a que el método es virtual, se llamará a la implementación de `DoWork(int)` en `Derived`.  Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#34](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_9.cs)]  
  
 Para obtener más ejemplos de `new` y de `override`, vea [Saber cuándo utilizar las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)