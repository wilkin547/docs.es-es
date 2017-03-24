---
title: "Clases y m&#233;todos parciales (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, clases y métodos parciales"
  - "clases parciales [C#]"
  - "métodos parciales [C#]"
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 35
---
# Clases y m&#233;todos parciales (Gu&#237;a de programaci&#243;n de C#)
Es posible dividir la definición de una [clase](../../../csharp/language-reference/keywords/class.md), [struct](../../../csharp/language-reference/keywords/struct.md), [interfaz](../../../csharp/language-reference/keywords/interface.md) o método en dos o más archivos de código fuente.  Cada archivo de código fuente contiene una sección de la definición de tipos o métodos, y todas las partes se combinan cuando se compila la aplicación.  
  
## Clases parciales  
 Existen diversas situaciones en las que es conveniente dividir una definición de clase:  
  
-   Al trabajar en proyectos grandes, el hecho de dividir una clase en archivos independientes permite que varios programadores trabajen al mismo tiempo con ella.  
  
-   Al trabajar con un código fuente generado automáticamente, se puede agregar el código a la clase sin tener que volver a crear el archivo de código fuente.  Visual Studio utiliza este enfoque al crear formularios Windows Forms, código contenedor de un servicio Web, etc.  Se puede crear código que utilice estas clases sin tener que modificar el archivo creado por Visual Studio.  
  
-   Para dividir una definición de clase, utilice el modificador [partial](../../../csharp/language-reference/keywords/partial-type.md), como se muestra a continuación:  
  
 [!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]  
  
 La palabra clave `partial` indica que otras partes de la clase, struct o interfaz se pueden definir en el espacio de nombres.  Todas las partes deben utilizar la palabra clave `partial`.  Todas las partes deben estar disponibles en tiempo de compilación para formar el tipo final.  Todas las partes deben tener la misma accesibilidad, ya sea `public`, `private`, etc.  
  
 Si alguna parte se declara abstracta, todo el tipo se considera abstracto.  Si alguna parte se declara sealed, todo el tipo se considera sealed.  Si alguna parte declara un tipo base, todo el tipo hereda esa clase.  
  
 Todas las partes que especifican una clase base deben concordar, pero las partes que omiten una clase base heredan igualmente el tipo base.  Las partes pueden especificar diferentes interfaces base, pero el tipo final implementa todas las interfaces mostradas por todas las declaraciones parciales.  Cualquier miembro de clase, struct o interfaz declarado en una definición parcial está disponible para todas las demás partes.  El tipo final es la combinación de todas las partes en tiempo de compilación.  
  
> [!NOTE]
>  El modificador `partial` no está disponible en declaraciones de delegado o enumeración.  
  
 El siguiente ejemplo muestra que los tipos anidados pueden ser parciales, aunque el tipo en el que están anidados no sea propiamente parcial.  
  
 [!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]  
  
 En tiempo de compilación, se combinan los atributos de definiciones de tipo parcial.  Por ejemplo, consideremos las siguientes declaraciones:  
  
 [!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]  
  
 Son equivalentes a las declaraciones siguientes:  
  
 [!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]  
  
 Los siguientes elementos se combinan a partir de todas las definiciones de tipo parcial:  
  
-   comentarios XML  
  
-   interfaces  
  
-   atributos de parámetro de tipo genérico  
  
-   atributos de clase  
  
-   miembros  
  
 Por ejemplo, consideremos las siguientes declaraciones:  
  
 [!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]  
  
 Son equivalentes a las declaraciones siguientes:  
  
 [!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]  
  
### Restricciones  
 Existen varias reglas que se deben seguir al trabajar con definiciones de clase parciales:  
  
-   Todas las definiciones de tipo parcial creadas para ser parte del mismo tipo deben modificarse con `partial`.  Por ejemplo, las siguientes declaraciones de clase generan un error:  
  
     [!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]  
  
-   El modificador `partial` sólo puede aparecer inmediatamente antes de las palabras clave `class`, `struct` o `interface`.  
  
-   Se permiten tipos parciales anidados en definiciones de tipo parcial, como se muestra en el siguiente ejemplo:  
  
     [!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]  
  
-   Todas las definiciones de tipo parcial que deben ser parte del mismo tipo deben definirse en el mismo ensamblado y el mismo módulo \(archivo .exe o .dll\).  Las definiciones parciales no pueden abarcar varios módulos.  
  
-   Los parámetros de nombre de clase y tipo genérico deben coincidir en todas las definiciones de tipo parcial.  Los tipos genéricos pueden ser parciales.  Todas las declaraciones parciales deben utilizar los mismos nombres de parámetro en el mismo orden.  
  
-   Las siguientes palabras clave en una definición de tipo parcial son opcionales, pero si hay alguna en una definición de tipo parcial, no puede entrar en conflicto con las palabras clave especificadas en otra definición parcial para el mismo tipo:  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   Clase base  
  
    -   modificador [new](../../../csharp/language-reference/keywords/new.md) \(partes anidadas\)  
  
    -   restricciones genéricas  
  
         Para obtener más información, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Ejemplo 1  
  
### Descripción  
 En el siguiente ejemplo, los campos y el constructor de la clase, `CoOrds`, se declaran en una definición de clase parcial, mientras que el miembro `PrintCoOrds` se declara en otra definición de clase parcial.  
  
### Código  
 [!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]  
  
## Ejemplo 2  
  
### Descripción  
 El siguiente ejemplo muestra que también se pueden desarrollar structs e interfaces parciales.  
  
### Código  
 [!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]  
  
## Métodos Partial  
 Una clase o struct parcial puede contener un método parcial.  Una parte de la clase contiene la firma del método.  Una implementación opcional se puede definir en la misma parte u otra parte.  Si no se proporciona la implementación, el método y todas las llamadas a él se quitan en tiempo de compilación.  
  
 Los métodos parciales permiten al implementador de una parte de una clase definir un método, de forma similar a un evento.  El implementador de la otra parte de la clase puede decidir si implementar el método o no.  Si no se implementa el método, el compilador quita la firma del método y todas las llamadas al método.  Las llamadas al método, incluidos los resultados ocurridos a partir de la evaluación de los argumentos en las llamadas, no tienen ningún efecto en tiempo de ejecución.  Por consiguiente, cualquier código en la clase parcial puede utilizar libremente un método parcial, aun cuando no se proporcione la implementación.  No se producirá ningún error en tiempo de compilación o en tiempo de ejecución si se realizan llamadas al método y éste no está implementado.  
  
 Los métodos parciales son especialmente útiles como una manera de personalizar el código generado.  Permiten reservar un nombre y una firma de método, de modo que el código generado pueda llamar al método y el programador pueda decidir si lo implementa o no.  De forma muy similar a las clases parciales, los métodos parciales permiten que el código creado por un generador de código y el código creado por un programador humano puedan funcionar juntos sin costes en tiempo de ejecución.  
  
 Una declaración de método parcial consta de dos partes: la definición y la implementación.  Éstas pueden estar en partes independientes de una clase parcial o en la misma parte.  Si no existe ninguna declaración de implementación, el compilador quita la declaración de definición y todas las llamadas al método.  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   Las declaraciones de método parciales deben comenzar con la palabra clave contextual [partial](../../../csharp/language-reference/keywords/partial-type.md), y el método debe devolver [void](../../../csharp/language-reference/keywords/void.md).  
  
-   Los métodos parciales pueden tener parámetros [ref](../../../csharp/language-reference/keywords/ref.md), pero no [out](../../../csharp/language-reference/keywords/out.md).  
  
-   Los métodos parciales son implícitamente [private](../../../csharp/language-reference/keywords/private.md) y, por consiguiente, no pueden ser [virtual](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Los métodos parciales no pueden ser [extern](../../../csharp/language-reference/keywords/extern.md), porque la presencia del cuerpo determina si son de definición o de implementación.  
  
-   Los métodos parciales pueden tener modificadores [static](../../../csharp/language-reference/keywords/static.md) y [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
-   Los métodos parciales pueden ser genéricos.  Las restricciones se colocan en la declaración de método parcial que realiza la definición, y se pueden repetir opcionalmente en la parte de implementación.  Los nombres de parámetros y parámetros de tipo no tienen que ser iguales en la declaración que realiza la implementación y en la que realiza la definición.  
  
-   Se puede crear un [delegado](../../../csharp/language-reference/keywords/delegate.md) de un método parcial que se ha definido e implementado, pero no de un método parcial que solo se ha definido.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [partial \(Tipos\)](../../../csharp/language-reference/keywords/partial-type.md)