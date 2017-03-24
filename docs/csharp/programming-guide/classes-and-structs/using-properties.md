---
title: "Utilizar propiedades (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "get (descriptor de acceso) [C#]"
  - "propiedades [C#], acerca de las propiedades"
  - "set (descriptor de acceso) [C#]"
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Utilizar propiedades (Gu&#237;a de programaci&#243;n de C#)
Las propiedades combinan aspectos de los campos y de los métodos.  Para el usuario de un objeto, una propiedad es similar a un campo, el acceso a la propiedad requiere la misma sintaxis.  Para el implementador de una clase, una propiedad es uno o dos bloques de código que representan un descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) y un descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md).  El bloque de código para el descriptor de acceso `get` se ejecuta cuando se lee la propiedad; el bloque de código para el descriptor de acceso `set` se ejecuta cuando se asigna un nuevo valor a la propiedad.  Una propiedad sin un descriptor de acceso `set` se considera de sólo lectura.  Una propiedad sin un descriptor de acceso `get` se considera de sólo escritura.  Una propiedad con ambos descriptores de acceso es de lectura y escritura.  
  
 A diferencia de los campos, las propiedades no están clasificadas como variables.  Por lo tanto, no se puede pasar una propiedad como un parámetro [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md).  
  
 Las propiedades tienen muchos usos: validan datos antes de permitir un cambio; exponen datos de forma transparente en una clase donde se recuperan realmente los datos de otro origen, como una base de datos; realizan una acción cuando se modifican datos, por ejemplo, provocar un evento, o cambian el valor de otros campos.  
  
 Las propiedades se declaran en el bloque de clase especificando el nivel de acceso del campo, seguido por el tipo de la propiedad, por el nombre de la propiedad y por un bloque de código que declara un descriptor de acceso `get` y\/o un descriptor de acceso `set`.  Por ejemplo:  
  
 [!code-cs[csProgGuideProperties#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_1.cs)]  
  
 En este ejemplo, `Month` se declara como una propiedad para que el descriptor de acceso `set` pueda asegurarse de que `Month` se establezca en un valor comprendido entre 1 y 12.  La propiedad `Month` utiliza un campo privado para realizar el seguimiento del valor real.  La ubicación real de los datos de una propiedad suele conocerse como "memoria auxiliar" de la propiedad. Es normal que las propiedades utilicen campos privados como memoria auxiliar.  El campo se marca como privado para asegurarse de que sólo puede cambiarse llamando a la propiedad.  Para obtener más información sobre restricciones de acceso público y privado, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Las propiedades autoimplementadas ofrecen una sintaxis simplificada para las declaraciones de propiedades simples.  Para obtener más información, consulte [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## El descriptor de acceso get  
 El cuerpo del descriptor de acceso `get` se parece al de un método.  Debe devolver el valor del tipo de la propiedad.  La ejecución del descriptor de acceso `get` equivale a leer el valor del campo.  Por ejemplo, cuando se devuelve la variable privada del descriptor de acceso `get` y las optimizaciones están habilitadas, el compilador pone la llamada al método del descriptor de acceso `get` entre líneas para que no se produzca una sobrecarga de método\-llamada.  Sin embargo, un método de descriptor de acceso `get` virtual no se puede poner entre líneas, porque el compilador no sabe en tiempo de compilación qué método puede llamarse en tiempo de ejecución.  A continuación, se muestra un descriptor de acceso `get` que devuelve el valor de un campo privado `name`:  
  
 [!code-cs[csProgGuideProperties#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_2.cs)]  
  
 Cuando se haga referencia a la propiedad, se llamará al descriptor de acceso `get` para leer el valor de la misma, salvo en el caso de que la referencia se haga como el destino de una asignación.  Por ejemplo:  
  
 [!code-cs[csProgGuideProperties#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_3.cs)]  
  
 El descriptor de acceso `get` debe terminar en una instrucción [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md), y el control no puede salir del cuerpo del descriptor de acceso.  
  
 Cambiar el estado de un objeto mediante el descriptor de acceso `get` es una técnica de programación poco recomendable.  Por ejemplo, el siguiente descriptor de acceso cambia, como efecto secundario, el estado del objeto cada vez que se obtiene acceso al campo `number`.  
  
 [!code-cs[csProgGuideProperties#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_4.cs)]  
  
 Se puede utilizar el descriptor de acceso `get` para devolver el valor de un campo o para calcularlo y devolverlo.  Por ejemplo:  
  
 [!code-cs[csProgGuideProperties#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_5.cs)]  
  
 El segmento de código anterior devolverá el valor NA si no se asigna ningún valor a la propiedad `Name`.  
  
## El descriptor de acceso set  
 El descriptor de acceso `set` es similar a un método cuyo tipo de valor devuelto es [void](../../../csharp/language-reference/keywords/void.md).  Utiliza un parámetro implícito denominado `value`, que tiene el mismo tipo que la propiedad.  En el siguiente ejemplo se agrega un descriptor de acceso `set` a la propiedad `Name`:  
  
 [!code-cs[csProgGuideProperties#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_6.cs)]  
  
 Cuando se asigne un valor a la propiedad, se llamará al descriptor de acceso `set` utilizando un argumento que proporcione el nuevo valor.  Por ejemplo:  
  
 [!code-cs[csProgGuideProperties#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_7.cs)]  
  
 No es correcto utilizar el nombre de parámetro implícito, `value`, para una declaración de variable local en un descriptor de acceso `set`.  
  
## Comentarios  
 Las propiedades pueden marcarse como `public`, `private`, `protected`, `internal` o `protected internal`.  Estos modificadores de acceso definen cómo pueden tener acceso a las propiedades los usuarios de la clase.  Los descriptores de acceso `get` y `set` para la misma propiedad pueden tener modificadores de acceso diferentes.  Por ejemplo, el descriptor de acceso `get` puede ser `public` para permitir el acceso de sólo lectura desde fuera del tipo, y el descriptor de acceso `set` puede ser `private` o `protected`.  Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Una propiedad puede declararse como propiedad estática mediante la palabra clave `static`.  Esto hace que la propiedad esté siempre disponible para los llamadores, aunque no exista ninguna instancia de la clase.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Una propiedad puede marcarse como propiedad virtual mediante la palabra clave [virtual](../../../csharp/language-reference/keywords/virtual.md).  Esto permite que las clases derivadas invaliden el comportamiento de la propiedad mediante la palabra clave [override](../../../csharp/language-reference/keywords/override.md).  Para obtener más información acerca de estas opciones, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Una propiedad que reemplaza una propiedad virtual también puede ser de tipo [sealed](../../../csharp/language-reference/keywords/sealed.md), lo cual especifica que ya no es virtual para las clases derivadas.  Por último, una propiedad puede declararse como [abstract](../../../csharp/language-reference/keywords/abstract.md).  Esto significa que no hay ninguna implementación en la clase, y las clases derivadas deben escribir su propia implementación.  Para obtener más información acerca de estas opciones, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
> [!NOTE]
>  No es correcto utilizar un modificador [virtual](../../../csharp/language-reference/keywords/virtual.md), [abstractas](../../../csharp/language-reference/keywords/abstract.md) o [override](../../../csharp/language-reference/keywords/override.md) en un descriptor de acceso de una propiedad [static](../../../csharp/language-reference/keywords/static.md).  
  
## Ejemplo  
 En este ejemplo se muestra el uso de propiedades de instancia, estáticas y de sólo lectura.  Lee el nombre del empleado escrito mediante el teclado, incrementa el número de empleados `NumberOfEmployees` en una unidad y muestra el nombre del empleado y su número correspondiente.  
  
 [!code-cs[csProgGuideProperties#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_8.cs)]  
  
## Ejemplo  
 En este ejemplo se muestra el método para tener acceso a una propiedad de una clase base que está oculta por otra propiedad con el mismo nombre de una clase derivada.  
  
 [!code-cs[csProgGuideProperties#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_9.cs)]  
  
 Es importante tener en cuenta los siguientes detalles del ejemplo anterior:  
  
-   La propiedad `Name` de la clase derivada oculta la propiedad `Name` de la clase base.  En este caso, se utiliza el modificador `new` en la declaración de la propiedad de la clase derivada:  
  
     [!code-cs[csProgGuideProperties#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_10.cs)]  
  
-   Se utiliza la conversión `(Employee)` para tener acceso a la propiedad oculta de la clase base:  
  
     [!code-cs[csProgGuideProperties#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_11.cs)]  
  
     Para obtener más información acerca de los miembros ocultos, consulte [new \(Modificador\)](../../../csharp/language-reference/keywords/new-modifier.md).  
  
## Ejemplo  
 En este ejemplo se utilizan dos clases, `Cube` y `Square` para implementar una clase abstracta, `Shape`, y reemplazar su propiedad abstracta `Area`.  Conviene resaltar que se utiliza el modificador [override](../../../csharp/language-reference/keywords/override.md) en las propiedades.  El programa lee el valor del lado como entrada y calcula las superficies del cuadrado y el cubo.  También lee el valor de la superficie como entrada y calcula el lado correspondiente del cuadrado y el cubo.  
  
 [!code-cs[csProgGuideProperties#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_12.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Propiedades de interfaz](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)   
 [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)