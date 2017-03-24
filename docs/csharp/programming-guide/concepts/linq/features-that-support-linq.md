---
title: "C# Features That Support LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], features supporting LINQ"
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# C# Features That Support LINQ
En la sección siguiente se presentan las nuevas construcciones de lenguaje incluidas en C\# 3.0.  Aunque todas estas nuevas características se utilizan hasta cierto punto con las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], no se limitan a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] y se pueden usar en cualquier contexto donde sean útiles.  
  
## Expresiones de consulta  
 Las expresiones de consulta utilizan una sintaxis declarativa similar a SQL o XQuery para consultar en colecciones IEnumerable.  En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a una implementación del proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] de los métodos de extensión de operador de consulta estándar.  Las aplicaciones controlan los operadores de consulta estándar que están en el ámbito especificando el espacio de nombres adecuado con una directiva `using`.  La expresión de consulta siguiente utiliza una matriz de cadenas, las agrupa por el primer carácter de la cadena y ordena los grupos.  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Para obtener más información, consulte [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## Variables con tipo implícito \(var\)  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, puede utilizar el modificador [var](../../../../csharp/language-reference/keywords/var.md) para indicar al compilador que deduzca y asigne el tipo, como se muestra a continuación:  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Las variables declaradas como `var` están tan fuertemente tipadas como las variables cuyo tipo se especifica explícitamente.  El uso de `var` permite crear tipos anónimos, pero se puede utilizar para cualquier variable local.  Las matrices también se pueden declarar con tipos implícitos.  
  
 Para obtener más información, consulte [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Inicializadores de objeto y colección  
 Los inicializadores de objeto y colección permiten inicializar los objetos sin llamar explícitamente a un constructor para el objeto.  Los inicializadores suelen usarse en expresiones de consulta cuando proyectan los datos de origen en un nuevo tipo de datos.  Si una clase denominada `Customer` tuviese las propiedades públicas `Name` y `Phone`, el inicializador de objeto se podría utilizar como en el código siguiente:  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Para obtener más información, consulte [Inicializadores de objeto y colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Tipos anónimos  
 Un tipo anónimo se construye en el compilador y el nombre del tipo sólo está disponible para el compilador.  Los tipos anónimos representan una manera cómoda de agrupar temporalmente un conjunto de propiedades en un resultado de consulta sin tener que definir un tipo con nombre independiente.  Los tipos anónimos se inicializan con una nueva expresión y un inicializador de objeto, como se muestra a continuación:  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Para obtener más información, consulte [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## Métodos de extensión.  
 Un método de extensión es un método estático que se puede asociar a un tipo de forma que se le puede llamar como si fuese un método de instancia en el tipo.  Esta característica de hecho permite "agregar" nuevos métodos a los tipos existentes sin tener que modificarlos realmente.  Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funcionalidad de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] para cualquier tipo que implementa <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Para obtener más información, consulte [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## Expresiones lambda  
 Una expresión lambda es una función inline que utiliza el operador \=\> para separar los parámetros de entrada del cuerpo de una función y que se puede convertir en tiempo de compilación en un delegado o un árbol de expresión.  En la programación en [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], encontrará expresiones lambda al realizar llamadas de métodos directas a los operadores de consulta estándar.  
  
 Para obtener más información, vea:  
  
-   [Funciones anónimas](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Expresiones lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)  
  
## Propiedades autoimplementadas  
 Las propiedades autoimplementadas hacen que la declaración de propiedades sea más concisa.  Al declarar una propiedad como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo que no está accesible excepto a través del método captador y establecedor de la propiedad.  
  
```  
public string Name {get; set;}  
```  
  
 Para obtener más información, consulte [Propiedades autoimplementadas](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Visual Basic Features That Support LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md)