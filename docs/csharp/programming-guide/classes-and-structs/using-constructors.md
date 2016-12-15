---
title: "Utilizar constructores (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "constructores [C#], acerca de constructores"
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar constructores (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cuando se crea [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), se llama al constructor.  Los constructores tienen el mismo nombre que la clase o struct, e inicializan normalmente los miembros de datos del nuevo objeto.  
  
 En el ejemplo siguiente, una clase denominada `Taxi` se define mediante un constructor simple.  Esta clase crea instancias con el operador [new](../../../csharp/language-reference/keywords/new.md).  El operador `new` invoca el constructor `Taxi` inmediatamente después de asignar la memoria al nuevo objeto.  
  
 [!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 Un constructor que no toma ningún parámetro se denomina *constructor predeterminado*.  Los constructores predeterminados se invocan cada vez que se crea una instancia de un objeto mediante el operador `new` y no se proporciona ningún argumento a `new`.  Para obtener más información, vea [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 A menos que la clase sea [estática](../../../csharp/language-reference/keywords/static.md), a las clases sin constructores se les asigna un constructor público predeterminado a través del compilador de C\# con el fin de habilitar la creación de instancias de clases.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Es posible evitar que se creen instancias de una clase mediante la conversión del constructor a privado, como se muestra a continuación:  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 Para obtener más información, vea [Constructores privados](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).  
  
 Los constructores para los tipos [struct](../../../csharp/language-reference/keywords/struct.md) son similares a los constructores de clases, pero los tipos `structs` no pueden contener un constructor predeterminado explícito porque el compilador proporciona uno automáticamente.  Este constructor inicializa cada campo del tipo `struct` con los valores predeterminados.  Para obtener más información, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  Sin embargo, este constructor predeterminado sólo se invoca si se crean instancias del tipo `struct` con `new`.  Por ejemplo, en este código se utiliza el constructor predeterminado para <xref:System.Int32>, lo que garantiza la inicialización del tipo entero:  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Sin embargo, el código siguiente genera un error del compilador porque no usa `new` e intenta utilizar un objeto que no se ha inicializado:  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 Como alternativa, se pueden inicializar objetos basados en `structs` \(incluidos todos los tipos numéricos integrados\) o asignarse y, a continuación, utilizarse como en el ejemplo siguiente:  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 En consecuencia no se requiere llamar al constructor predeterminado para un tipo de valor.  
  
 Tanto las clases como las `structs` pueden definir constructores que acepten parámetros.  Se debe llamar a constructores que toman parámetros a través de una instrucción `new` o [base](../../../csharp/language-reference/keywords/base.md).  Las clases y las `structs` también pueden definir varios constructores y no se requiere ninguno para definir un constructor predeterminado.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 Esta clase se puede crear mediante cualquiera de las siguientes instrucciones:  
  
 [!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 Cualquier constructor puede utilizar la palabra clave `base` para llamar al constructor de una clase base.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 En este ejemplo, se llama al constructor de la clase base antes de ejecutar el bloque del constructor.  La palabra clave `base` se puede utilizar con o sin parámetros.  Cualquier parámetro del constructor se puede utilizar como parámetro de `base` o como parte de una expresión.  Para obtener más información, vea [base](../../../csharp/language-reference/keywords/base.md).  
  
 En una clase derivada, si no se llama explícitamente al constructor de la clase base mediante la palabra clave `base`, se llamará implícitamente al constructor predeterminado, si existe alguno.  Esto significa que las siguientes declaraciones del constructor son efectivamente las mismas:  
  
 [!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 Si una clase base no proporciona un constructor predeterminado, la clase derivada debe realizar una llamada explícita a un constructor base mediante `base`.  
  
 Un constructor puede invocar a otro constructor en el mismo objeto mediante la palabra clave [this](../../../csharp/language-reference/keywords/this.md).  Al igual que `base`, `this` se puede utilizar con o sin parámetros y cualquier parámetro en el constructor está disponible como parámetro para `this` o como parte de una expresión.  Por ejemplo, el segundo constructor del ejemplo anterior se puede rescribir con `this`:  
  
 [!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 El uso de la palabra clave `this` en el ejemplo anterior hace que se llame a este constructor:  
  
 [!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 Los constructores se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected` `internal`.  Estos modificadores de acceso definen cómo los usuarios de la clase pueden construir la clase.  Para obtener más información, vea [Modificadores de acceso \(Guía de programación de C\#\)](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Un constructor se puede declarar como estático mediante la palabra clave [static](../../../csharp/language-reference/keywords/static.md).  Se llama automáticamente a los constructores estáticos de forma inmediata antes de que se tenga acceso a cualquier campo estático, y, generalmente, se utilizan para inicializar los miembros de clase estáticos.  Para obtener más información, vea [Constructores estáticos \(Guía de programación de C\#\)](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)