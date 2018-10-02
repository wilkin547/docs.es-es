---
title: Características de C# compatibles con LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: c617b2d7b56618867fe92cbe1d9ee04aa4c3ab64
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207244"
---
# <a name="c-features-that-support-linq"></a>Características de C# compatibles con LINQ
La siguiente sección presenta las nuevas construcciones de lenguaje incluidas en C# 3.0. Aunque estas nuevas características se usan hasta cierto punto con consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], no se limitan a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] y se pueden usar en cualquier contexto en las que se consideren de utilidad.  
  
## <a name="query-expressions"></a>Expresiones de consulta  
 Las expresiones de consulta usan una sintaxis declarativa similar a SQL o XQuery para consultar colecciones de IEnumerable. En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] de los métodos de extensión de operador de consulta estándar. Las aplicaciones controlan los operadores de consulta estándar que están en el ámbito al especificar el espacio de nombres adecuado con una directiva `using`. La siguiente expresión de consulta toma una matriz de cadenas, las agrupa por el primer carácter de la cadena y ordena los grupos.  
  
```csharp  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Para obtener más información, vea [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## <a name="implicitly-typed-variables-var"></a>Variables con asignación implícita de tipos (var)  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, se puede usar el modificador [var](../../../../csharp/language-reference/keywords/var.md) para indicar al compilador que deduzca y asigne el tipo, como se muestra aquí:  
  
```csharp  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Las variables declaradas como `var` son tan fuertemente tipadas como las variables cuyo tipo se especifica explícitamente. El uso de `var` hace posible crear tipos anónimos, pero solo se puede usar para variables locales. También se pueden declarar matrices con asignación implícita de tipos.  
  
 Para más información, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="object-and-collection-initializers"></a>Inicializadores de objeto y colección  
 Los inicializadores de objeto y colección permiten inicializar objetos sin llamar explícitamente a un constructor para el objeto. Los inicializadores normalmente se usan en expresiones de consulta cuando proyectan los datos de origen en un nuevo tipo de datos. Suponiendo que hay una clase denominada `Customer` con las propiedades públicas `Name` y `Phone`, el inicializador de objeto se puede usar como en el código siguiente:  
  
```csharp  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Para más información, vea [Inicializadores de objeto y de colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Un tipo anónimo se construye por el compilador y el nombre del tipo solo está disponible para el compilador. Los tipos anónimos son una manera cómoda de agrupar un conjunto de propiedades temporalmente en un resultado de consulta sin tener que definir un tipo con nombre independiente. Los tipos anónimos se inicializan con una nueva expresión y un inicializador de objeto, como se muestra aquí:  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Para obtener más información, vea [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="extension-methods"></a>Métodos de extensión.  
 Un método de extensión es un método estático que se puede asociar con un tipo, por lo que puede llamarse como si fuera un método de instancia en el tipo. Esta característica permite, en efecto, "agregar" nuevos métodos a los tipos existentes sin tener que modificarlos realmente. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funciones de consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Para más información, vea [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 Una expresión lambda es una función insertada que usa el operador => para separar los parámetros de entrada del cuerpo de la función y que se puede convertir en tiempo de compilación en un delegado o un árbol de expresión. En la programación de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], encontrará expresiones lambda al realizar llamadas de método directas a los operadores de consulta estándar.  
  
 Para obtener más información, consulte:  
  
-   [Funciones anónimas](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Expresiones lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Árboles de expresión (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a>Propiedades autoimplementadas  
 Las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa. Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede tener acceso con el captador y el establecedor de la propiedad.  
  
```csharp  
public string Name {get; set;}  
```  
  
 Para obtener más información, vea [Propiedades implementadas automáticamente](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
