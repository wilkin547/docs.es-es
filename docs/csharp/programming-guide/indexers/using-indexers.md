---
title: "Utilizar indizadores (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "indizadores [C#], acerca de indizadores"
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar indizadores (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los indizadores suponen una comodidad sintáctica al permitir crear una [clase](../../../csharp/language-reference/keywords/class.md), [struct](../../../csharp/language-reference/keywords/struct.md) o [interfaz](../../../csharp/language-reference/keywords/interface.md) a las que las aplicaciones cliente pueden tener acceso como si se tratara de una matriz.  Por lo general, los indizadores se implementan en tipos cuya finalidad principal es encapsular una matriz o colección interna.  Supongamos, por ejemplo, que tiene una clase denominada TempRecord que representa la temperatura en grados Fahrenheit que se registra en 10 momentos diferentes durante un período de 24 horas.  La clase contiene una matriz denominada "temps" de tipo float para representar las temperaturas y un objeto <xref:System.DateTime> que representa la fecha en la que se registraron las temperaturas.  Al implementar un indizador en esta clase, los clientes pueden tener acceso a las temperaturas en una instancia de TempRecord como `float temp = tr[4]` y no como `float temp = tr.temps[4]`.  La notación del indizador no sólo simplifica la sintaxis de las aplicaciones cliente, sino que también hace la clase y su finalidad más intuitivas para que otros programadores lo entiendan.  
  
 Para declarar un indizador en una clase o struct, utilice la palabra clave [this](../../../csharp/language-reference/keywords/this.md), como en este ejemplo:  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
  
```  
  
## Comentarios  
 El tipo de un indizador y el tipo de sus parámetros deben ser por lo menos tan accesibles como el propio indizador.  Para más información acerca de los niveles de accesibilidad, vea [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Para obtener más información sobre cómo utilizar los indizadores con una interfaz, vea [Indizadores en interfaces](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).  
  
 La firma de un indizador está formada por el número de parámetros formales y sus tipos.  No incluye el tipo de indizador ni los nombres de los parámetros formales.  Si se declara más de un indizador en una misma clase, cada indizador deberá tener una firma diferente.  
  
 Los valores de un indizador no se clasifican como variables; por ello, no es posible transferir un valor de indizador como un parámetro [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md).  
  
 Para proporcionar un nombre al indizador que otros lenguajes puedan utilizar, use un atributo `name` en la declaración.  Por ejemplo:  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 Este indizador tendrá el nombre `TheItem`.  Si no se proporciona el atributo con nombre, se le dará como nombre predeterminado `Item`.  
  
## Ejemplo 1  
  
### Descripción  
 En el ejemplo siguiente se muestra cómo declarar un campo de matriz privado, `temps`, y un indizador.  El indizador permite tener acceso directo a la instancia `tempRecord[i]`.  La alternativa a utilizar el indizador es declarar la matriz como miembro de tipo [public](../../../csharp/language-reference/keywords/public.md) y tener acceso directamente a sus miembros, `tempRecord.temps[i]`.  
  
 Conviene tener en cuenta que cuando se evalúa el acceso de un indizador, por ejemplo, en una instrucción `Console.Write` se llama al descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md).  Por ello, si no existe un descriptor de acceso `get` se producirá un error en tiempo de compilación.  
  
### Código  
 [!code-cs[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]  
  
## Indizar utilizando otros valores  
 C\# no limita el tipo de índice al entero.  Por ejemplo, puede ser útil utilizar una cadena con un indizador.  Este tipo de indizador podría implementarse buscando la cadena dentro de la colección y devolviendo el valor adecuado.  Como se pueden sobrecargar los descriptores de acceso, es posible la coexistencia de cadenas y enteros.  
  
## Ejemplo 2  
  
### Descripción  
 En este ejemplo, se declara una clase que almacena los días de la semana.  Se declara un descriptor de acceso `get` que toma una cadena, el nombre de un día, y devuelve el entero correspondiente.  Por ejemplo, Sunday devolverá 0, Monday devolverá 1, y así sucesivamente.  
  
### Código  
 [!code-cs[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]  
  
## Programación sólida  
 Fundamentalmente, hay dos maneras de mejorar la seguridad y confiabilidad de los indizadores:  
  
-   Asegúrese de incorporar algún tipo de estrategia de control de errores para tratar la posibilidad de que el código de cliente pase un valor de índice no válido.  En el primer ejemplo de este tema, la clase TempRecord proporciona una propiedad Length que permite al código de cliente comprobar la entrada antes de pasarla al indizador.  También puede incluir el código de control de errores en el propio indizador.  No olvide documentar a los usuarios cualquier excepción que se produjera dentro de un descriptor de acceso de indizadores.  
  
-   Establezca la accesibilidad de los descriptores de acceso `get` y [set](../../../csharp/language-reference/keywords/set.md) para que sea lo más restrictiva posible.  Es importante particularmente para el descriptor de acceso `set`.  Para obtener más información, vea [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)