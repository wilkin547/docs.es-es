---
title: "Tipos de enumeraci&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "marcas de bits [C#]"
  - "Lenguaje C#, enumeraciones"
  - "enumeraciones [C#]"
  - "enumeraciones [C#]"
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Tipos de enumeraci&#243;n (Gu&#237;a de programaci&#243;n de C#)
Un tipo de enumeración \(también denominado enumeración o enum\) proporciona una manera eficaz de definir un conjunto de constantes integrales con nombre que pueden asignarse a una variable.  Por ejemplo, suponga que tiene que definir una variable cuyo valor representará un día de la semana.  Sólo hay siete valores significativos que almacenará dicha variable.  Para definir esos valores, puede utilizar un tipo de enumeración, que se declara mediante la palabra clave [enum](../../csharp/language-reference/keywords/enum.md).  
  
 [!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]  
  
 De forma predeterminada, el tipo subyacente de cada elemento de la enumeración es [int](../../csharp/language-reference/keywords/int.md).  Puede especificar otro tipo numérico integral utilizando dos puntos, como se muestra en el ejemplo anterior.  Para obtener una lista completa de los tipos posibles, vea [enum \(Referencia de C\#\)](../../csharp/language-reference/keywords/enum.md).  
  
 Puede comprobar los valores numéricos subyacentes convertir en el tipo subyacente, como se muestra en el ejemplo siguiente.  
  
```c#  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 A continuación se describen las ventajas de utilizar una enumeración en lugar de un tipo numérico:  
  
-   Se especifica claramente para el código de cliente qué valores son válidos para la variable.  
  
-   En [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)], IntelliSense muestra los valores definidos.  
  
 Si no se especifican valores para los elementos en la lista de enumeradores, los valores se incrementan automáticamente en 1.  En el ejemplo anterior, `Days.Sunday` tiene un valor de 0, `Days.Monday` tiene un valor de 1, y así sucesivamente.  Al crear un nuevo objeto `Days`, éste tendrá un valor predeterminado de `Days.Sunday` \(0\) si no se le asigna un valor explícitamente.  Al crear una enumeración, seleccione el valor predeterminado más lógico y asígnele el valor cero.  De esta forma, todas las enumeraciones tendrán ese valor predeterminado si no se les asigna un valor explícitamente al crearlas.  
  
 Si la variable `meetingDay` es de tipo `Days`, \(sin una conversión explícita\) sólo puede asignarle uno de los valores definido por `Days`.  Además, si cambia el día de la reunión, puede asignar un nuevo valor de `Days` a `meetingDay`:  
  
 [!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]  
  
> [!NOTE]
>  Es posible asignar un valor entero cualquiera a `meetingDay`.  Por ejemplo, esta línea de código no genera un error: `meetingDay = (Days) 42`.  Sin embargo, se recomienda no hacerlo, ya que la expectativa implícita es que una variable de enumeración contenga solamente uno de los valores definidos por la enumeración.  La asignación de un valor arbitrario a una variable de un tipo de enumeración presenta un alto riesgo de errores.  
  
 Puede asignar cualquier valor a los elementos de la lista de enumeradores de un tipo de enumeración; además, también puede utilizar valores calculados:  
  
 [!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]  
  
## Tipos de enumeración como marcadores de bits  
 Puede utilizar un tipo de enumeración para definir marcadores de bits, lo que permite que una instancia del tipo de enumeración almacene cualquier combinación de los valores definidos en la lista de enumeradores.  \(Por supuesto, puede que algunas combinaciones no tengan sentido o no se permitan en el código del programa.\)  
  
 Para crear una enumeración de marcadores de bits, aplique el atributo <xref:System.FlagsAttribute?displayProperty=fullName> y defina los valores de forma adecuada de manera que se puedan realizar en ellos las operaciones bit a bit de tipo `AND`, `OR`, `NOT` y `XOR`.  En una enumeración de marcadores de bits, incluya una constante con nombre de valor cero que signifique que "no se ha establecido ningún marcador". No asigne a un marcador el valor cero si éste no significa "no se ha establecido ningún marcador".  
  
 En el ejemplo siguiente, se define otra versión de la enumeración `Days`, que se denomina `Days2`.  `Days2` tiene el atributo `Flags` y a cada valor se le asigna la siguiente potencia mayor que 2.  Esto le permite crear una variable `Days2` cuyos valores son `Days2.Tuesday` y `Days2.Thursday`.  
  
 [!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]  
  
 Para establecer una marca en una enumeración, utilice el operador `OR` bit a bit como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]  
  
 Para determinar si se ha establecido una marca específica, use una operación `AND` bit a bit, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]  
  
 Para obtener más información sobre los aspectos que debe tener en cuenta al definir tipos de enumeración con el atributo <xref:System.FlagsAttribute?displayProperty=fullName>, vea <xref:System.Enum?displayProperty=fullName>.  
  
## Utilizar métodos System.Enum para detectar y manipular valores de enumeración  
 Todas las enumeraciones son instancias del tipo <xref:System.Enum?displayProperty=fullName>.  No puede derivar clases nuevas de <xref:System.Enum?displayProperty=fullName>, pero puede utilizar sus métodos para detectar información relacionada y manipular los valores de una instancia de enumeración.  
  
 [!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]  
  
 Para obtener más información, vea <xref:System.Enum?displayProperty=fullName>.  
  
 También puede crear un método nuevo para una enumeración a través de un método de extensión.  Para obtener más información, vea [Cómo: Crear un método nuevo para una enumeración](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).  
  
## Capítulo destacado del libro  
 [Más información sobre variables](http://go.microsoft.com/fwlink/?LinkId=221230) en [Principio Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Vea también  
 <xref:System.Enum?displayProperty=fullName>   
 [Guía de programación de C\#](../../csharp/programming-guide/index.md)   
 [enum](../../csharp/language-reference/keywords/enum.md)