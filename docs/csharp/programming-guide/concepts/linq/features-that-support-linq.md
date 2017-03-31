---
title: "Características de C# compatibles con LINQ | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f844e967e2abb7ea23e04a797017261e33bb4d75
ms.lasthandoff: 03/13/2017

---
# <a name="c-features-that-support-linq"></a>Características de C# compatibles con LINQ
La siguiente sección presenta las nuevas construcciones de lenguaje incluidas en C# 3.0. Aunque estas nuevas características se usan hasta cierto punto con consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], no se limitan a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] y se pueden usar en cualquier contexto en las que se consideren de utilidad.  
  
## <a name="query-expressions"></a>Expresiones de consulta  
 Las expresiones de consulta usan una sintaxis declarativa similar a SQL o XQuery para consultar colecciones de IEnumerable. En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] de los métodos de extensión de operador de consulta estándar. Las aplicaciones controlan los operadores de consulta estándar que están en el ámbito al especificar el espacio de nombres adecuado con una directiva `using`. La siguiente expresión de consulta toma una matriz de cadenas, las agrupa por el primer carácter de la cadena y ordena los grupos.  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Para obtener más información, vea [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## <a name="implicitly-typed-variables-var"></a>Variables con asignación implícita de tipos (var)  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, se puede usar el modificador [var](../../../../csharp/language-reference/keywords/var.md) para indicar al compilador que deduzca y asigne el tipo, como se muestra aquí:  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Las variables declaradas como `var` son tan fuertemente tipadas como las variables cuyo tipo se especifica explícitamente. El uso de `var` hace posible crear tipos anónimos, pero se puede usar para cualquier variable local. También se pueden declarar matrices con asignación implícita de tipos.  
  
 Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="object-and-collection-initializers"></a>Inicializadores de objeto y colección  
 Los inicializadores de objeto y colección permiten inicializar objetos sin llamar explícitamente a un constructor para el objeto. Los inicializadores normalmente se usan en expresiones de consulta cuando proyectan los datos de origen en un nuevo tipo de datos. Suponiendo que hay una clase denominada `Customer` con las propiedades públicas `Name` y `Phone`, el inicializador de objeto se puede usar como en el código siguiente:  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Para obtener más información, vea [Inicializadores de objeto y colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Un tipo anónimo se construye por el compilador y el nombre del tipo solo está disponible para el compilador. Los tipos anónimos son una manera cómoda de agrupar un conjunto de propiedades temporalmente en un resultado de consulta sin tener que definir un tipo con nombre independiente. Los tipos anónimos se inicializan con una nueva expresión y un inicializador de objeto, como se muestra aquí:  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Para obtener más información, vea [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="extension-methods"></a>métodos de extensión.  
 Un método de extensión es un método estático que se puede asociar con un tipo, por lo que puede llamarse como si fuera un método de instancia en el tipo. Esta característica permite, en efecto, "agregar" nuevos métodos a los tipos existentes sin tener que modificarlos realmente. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funcionalidad de consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Para obtener más información, vea [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 Una expresión lambda es una función insertada que usa el operador => para separar los parámetros de entrada del cuerpo de la función y que se puede convertir en tiempo de compilación en un delegado o un árbol de expresión. En la programación de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], encontrará expresiones lambda al realizar llamadas de método directas a los operadores de consulta estándar.  
  
 Para obtener más información, consulte:  
  
-   [Funciones anónimas](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Expresiones lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Árboles de expresión (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a>Propiedades autoimplementadas  
 Las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa. Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede tener acceso con el captador y el establecedor de la propiedad.  
  
```  
public string Name {get; set;}  
```  
  
 Para obtener más información, vea [Propiedades implementadas automáticamente](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
