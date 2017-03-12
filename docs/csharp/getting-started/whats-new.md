---
title: "Novedades de Visual C# | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 9f18dc26-27fa-4603-a639-b573f07a117b
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 39
---
# Novedades de Visual C# #
Esta página enumera los nombres de las características clave de cada versión de C\# con descripciones de las características nuevas y mejoradas de la versión más reciente del lenguaje.  
  
## Versiones anteriores  
 C\# 1, Visual Studio .NET 2002  
 Primera versión  
  
 C\# 1.1, Visual Studio .NET 2003  
 Pragma `#line` y comentarios de documentos xml  
  
 C\# 2, Visual Studio .NET 2005  
 Métodos anónimos, genéricos, tipos que aceptan valores NULL, iteradores\/rendimiento, clases `static`, covarianza\/contravarianza para delegados  
  
 C\# 3, Visual Studio .NET 2008  
 Inicializadores de objeto y colección, expresiones lambda, métodos de extensión, tipos anónimos, propiedades automáticas, Language Integrated Query \(LINQ\), tipos anónimos, inferencia de tipo de `var` local, LINQ  
  
 C\# 4, Visual Studio .NET 2010  
 `Dynamic`, argumentos con nombre, parámetros opcionales, covarianza\/contravarianza genérica  
  
 C\# 5, Visual Studio .NET 2012  
 `Async` \/ `await`, atributos de la información del llamador  
  
 Visual Studio .NET 2013  
 Correcciones de errores, mejoras de rendimiento y vistas previas de tecnología de .NET Compiler Platform \(«Roslyn»\)  
  
 C\# 6, Visual Studio .NET 2015  
 Versión actual, véase más abajo  
  
## Versión actual  
 [nameof](../../csharp/language-reference/keywords/nameof.md)  
 Puede obtener el nombre de cadena no calificado de un tipo o miembro para usarlo en un mensaje de error sin codificar de forma rígida una cadena.  Esto permite que el código siga siendo correcto al refactorizarlo.  Esta característica también es útil para enlazar los vínculos MVC del controlador de vista de modelos y desencadenar eventos de propiedad cambiada.  
  
 [Interpolación de cadenas](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Puede usar expresiones de interpolación de cadenas para construir cadenas.  Una expresión de cadena interpolada es similar a una cadena de plantilla que contiene expresiones.  C\# crea una cadena reemplazando las expresiones por las representaciones ToString de los resultados de las expresiones.  Una cadena interpolada es más fácil de entender con respecto a los argumentos que el [Formatos compuestos](../Topic/Composite%20Formatting.md).  
  
 [Acceso a miembros e indexación condicional null](../../csharp/language-reference/operators/null-conditional-operators.md)  
 Puede probar si hay valores null de forma sintáctica ligera antes de realizar una operación de acceso a miembros \(`?.`\) o índice \(`?[]`\).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  Si la referencia de objeto u operando izquierdo es null, la operación devuelve null.  
  
 [Inicializadores de índice](../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 Ahora puede inicializar elementos específicos de una colección que admita indexación, por ejemplo inicializar un diccionario.  
  
 [Inicializador de colección y métodos de extensión Add](../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 Ahora puede usar inicializadores para colecciones cuando la colección tenga un método de extensión Add.  Antes, el método Add tenía que ser un método de instancia.  
  
 **Resolución de sobrecargas**  
 El compilador mejoró la resolución de sobrecargas, de modo que produce más código mientras funciona de la manera esperada.  Es posible que deje de advertir un problema al elegir entre sobrecargas que toman los tipos de valor que aceptan valores NULL, o al pasar grupos de métodos \(en lugar de expresiones lambda\) a las sobrecargas que toman delegados.  
  
 [Filtros de excepciones](../../csharp/language-reference/keywords/try-catch.md)  
 Puede usar filtros de excepciones en cláusulas `catch` para determinar si una cláusula Catch debe controlar la excepción.  Sin esta característica, tiene que volver a producir la excepción, lo que recorta la pila de llamadas que se muestra en la excepción que se volvió a producir.  
  
 [Await en bloques Catch y Finally](../../csharp/language-reference/keywords/try-catch.md)  
 Puede usar `await` en cláusulas `catch` y `finally`.  
  
 [Inicializadores de propiedades automáticas](../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
 Ahora puede inicializar propiedades automáticas de forma similar a como se inicializan los campos.  
  
 [Propiedades automáticas de solo captador](../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
 Ahora es posible definir propiedades automáticas de solo lectura sin tener que definir una propiedad con la sintaxis de propiedad completa.  Se puede inicializar la propiedad donde se declara o en el constructor del tipo.  
  
 **Miembros de función con cuerpos de expresión**  
 Puede declarar miembros con cuerpos de expresión de código en la misma sintaxis ligera que se usa con expresiones lambda.  Consulte [Métodos](../../csharp/programming-guide/classes-and-structs/methods.md), [Propiedades](../../csharp/programming-guide/classes-and-structs/properties.md), [Indizadores](../../csharp/programming-guide/indexers/index.md) y [Operadores sobrecargables](../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).  
  
 [Uso de versión estática](../../csharp/language-reference/keywords/using-directive.md)  
 Puede importar miembros estáticos accesibles de tipos estáticos, de modo que pueda hacer referencia a los miembros sin calificar el acceso con el nombre del tipo.  
  
## Vea también  
 [Novedades de Visual Studio 2015](/visual-studio/ide/what-s-new-in-visual-studio-2015)