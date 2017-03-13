---
title: "Conversiones de tipos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "conversión [C#]"
  - "conversiones [C#], tipo"
  - "convertir tipos [C#]"
  - "conversión de tipos de datos [C#]"
  - "conversiones numéricas [C#]"
  - "conversión de tipos [C#]"
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 52
---
# Conversiones de tipos (Gu&#237;a de programaci&#243;n de C#)
Dado que a C\# se le asignan tipos estáticos en tiempo de compilación, después de declarar una variable, no se puede volver a declarar ni tampoco utilizar para almacenar valores de otro tipo, a menos que dicho tipo pueda convertirse en el tipo de la variable.  Por ejemplo, no existe conversión de un entero a una cadena arbitraria cualquiera.  Por lo tanto, después de declarar `i` como entero, no puede asignarle la cadena "Hello", como se muestra en el código siguiente.  
  
```c#  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 Sin embargo, en ocasiones puede que sea necesario copiar un valor en un parámetro de método o variable de otro tipo.  Por ejemplo, puede que tenga una variable de tipo entero que deba pasar a un método cuyo parámetro es de tipo `double`.  O bien, puede que necesite asignar una variable de clase a una variable de un tipo de interfaz.  Estos tipos de operaciones se denominan *conversiones de tipos*.  En C\#, puede realizar los siguientes tipos de conversiones:  
  
-   **Conversiones implícitas**: no se requiere una sintaxis especial porque la conversión se realiza con seguridad de tipos y no se perderán datos.  Entre los ejemplos se incluyen las conversiones de tipos enteros de menor a mayor y las conversiones de clases derivadas en clases base.  
  
-   **Conversiones explícitas \(conversiones de tipos\)**: las conversiones explícitas requieren un operador de conversión.  La conversión se requiere cuando es posible que se pierda información en el proceso o cuando esta puede no realizarse correctamente por otras razones. Entre los ejemplos habituales se incluye la conversión en un tipo con menor precisión o un intervalo menor, y la conversión de una instancia de clase base en una clase derivada.  
  
-   **Conversiones definidas por el usuario**: las conversiones definidas por el usuario se realizan a través de métodos especiales que puede definir para habilitar las conversiones explícitas e implícitas entre tipos personalizados que no tienen una relación de clase base\-clase derivada.  Para obtener más información, vea [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
-   **Conversiones con clases auxiliares**: para realizar conversiones entre tipos no compatibles, como los enteros y los objetos <xref:System.DateTime?displayProperty=fullName>, o bien cadenas hexadecimales y matrices de bytes, puede utilizar la clase <xref:System.BitConverter?displayProperty=fullName>, la clase <xref:System.Convert?displayProperty=fullName> y los métodos `Parse` de los tipos numéricos integrados, como <xref:System.Int32.Parse%2A?displayProperty=fullName>.  Para obtener más información, vea [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) y [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## Conversiones implícitas  
 En los tipos numéricos integrados, puede realizarse una conversión implícita cuando el valor que se va a almacenar puede ajustarse a la variable sin necesidad de truncamiento o redondeo.  Por ejemplo, una variable de tipo [long](../../../csharp/language-reference/keywords/long.md) \(entero de 8 bytes\) puede almacenar cualquier valor que pueda almacenar a su vez un elemento [int](../../../csharp/language-reference/keywords/int.md) \(4 bytes en un equipo de 32 bits\).  En el ejemplo siguiente, el compilador convierte implícitamente el valor de la derecha en un tipo `long` antes de asignarlo a `bigNum`.  
  
 [!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 Para obtener una lista completa de todas las conversiones numéricas implícitas, vea [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 En los tipos de referencia, siempre existe una conversión implícita desde una clase a cualquiera de sus interfaces o clases base directas o indirectas.  No se requiere una sintaxis especial, ya que una clase derivada siempre contiene todos los miembros de una clase base.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## Conversiones explícitas  
 Sin embargo, si no se puede realizar una conversión sin riesgo de perder información, el compilador requiere que se realice una conversión explícita, denominada *conversión de tipo*.  Una conversión de tipo es una manera de informar al compilador de forma explícita de que pretende realizar la conversión y que está al tanto de que puede producirse una pérdida de datos.  Para realizar una conversión de tipo, especifique entre paréntesis el tipo al que se va a aplicar dicha conversión delante del valor o la variable que se va a convertir.  El programa siguiente convierte un tipo [double](../../../csharp/language-reference/keywords/double.md) a un tipo [int](../../../csharp/language-reference/keywords/int.md).  El programa no se compilará sin el operador de conversión de tipo.  
  
 [!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 Para obtener una lista de las conversiones numéricas explícitas permitidas, vea [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
 En los tipos de referencia, se requiere una conversión explícita si debe convertir de un tipo base a un tipo derivado:  
  
```c#  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Una operación de conversión entre tipos de referencia no cambia el tipo en tiempo de ejecución del objeto subyacente; solo cambia el tipo del valor que se utiliza como referencia para ese objeto.  Para obtener más información, vea [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## Excepciones de las conversiones de tipos en tiempo de ejecución  
 En algunas conversiones de tipos de referencia, el compilador no puede determinar si será válida una conversión de tipo.  Es posible que una operación de conversión de tipo que se compila correctamente provoque un error en tiempo de ejecución.  Como se muestra en el ejemplo siguiente, una conversión de tipo que origine un error en tiempo de ejecución hará que se produzca una excepción <xref:System.InvalidCastException>.  
  
 [!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C\# proporciona los operadores [is](../../../csharp/language-reference/keywords/is.md) y [as](../../../csharp/language-reference/keywords/as.md), que permiten comprobar la compatibilidad antes de realizar una conversión de tipo.  Para obtener más información, vea [Cómo: Realizar conversiones seguras usando los operadores is y as](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Capítulo destacado del libro  
 [Más información sobre variables](http://go.microsoft.com/fwlink/?LinkId=221230) en [Principio Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [\(\) \(operador\)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [explícita](../../../csharp/language-reference/keywords/explicit.md)   
 [implícita](../../../csharp/language-reference/keywords/implicit.md)   
 [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [Generalized Type Conversion](../Topic/Generalized%20Type%20Conversion.md)   
 [Exported Type Conversion](http://msdn.microsoft.com/es-es/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)   
 [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)