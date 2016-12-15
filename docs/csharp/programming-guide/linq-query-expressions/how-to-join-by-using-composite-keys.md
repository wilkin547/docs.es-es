---
title: "C&#243;mo: Realizar una uni&#243;n usando claves compuestas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "claves compuestas [LINQ en C#]"
  - "combinaciones [C#]"
  - "combinaciones [C#], claves compuestas"
  - "consultas [LINQ en C#], combinaciones"
  - "expresiones de consulta [LINQ en C#], combinaciones"
ms.assetid: 3e015b3f-9cca-4b0c-aa97-dca0d36ea592
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Realizar una uni&#243;n usando claves compuestas (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo muestra cómo realizar operaciones de unión \(join\) con más de una clave para definir una coincidencia.  Esto se logra utilizando una clave compuesta.  Una clave compuesta se crea como un tipo anónimo o un tipo con nombre que incluye los valores con los que se desea comparar.  Si la variable de consulta se va a pasar entre métodos, utilice un tipo con nombre que invalide a <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> para la clave.  Los nombres de las propiedades, y el orden en el que ocurren, deben ser idénticos en cada clave.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar una clave compuesta para unir datos de tres tablas:  
  
```  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,         d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 La inferencia de tipos en claves compuestas depende de los nombres de las propiedades en las claves y del orden en el que ocurren.  Si las propiedades en las secuencias de origen no tienen los mismos nombres, deberá asignar nuevos nombres en las claves.  Por ejemplo, si la tabla `Orders` y la tabla `OrderDetails` utilizan cada una nombres diferentes para sus columnas, podría crear claves compuestas asignando nombres idénticos en los tipos anónimos:  
  
```  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 Las claves compuestas también se pueden utilizar en una cláusula `group`.  
  
## Compilar el código  
  
-   Para compilar y ejecutar este código, siga estos pasos:  
  
-   Abra [Cómo: Conectar con la base de datos Northwind](../Topic/How%20to:%20Connect%20to%20the%20Northwind%20Database.md) y siga las instrucciones para configurar el proyecto y crear la conexión de base de datos.  Para obtener más información, vea [Cómo: Instalar bases de datos de ejemplo](../Topic/How%20to:%20Install%20Sample%20Databases.md).  
  
-   En samples.cs, cree un nuevo método vacío que tome un parámetro de entrada de Northwind denominado db \(de forma similar a los otros métodos de ese archivo\).  Pegue el código de este ejemplo en el cuerpo del método.  
  
-   Modifique program.cs para llamar al nuevo método desde `Main`.  
  
-   Presione F5 para compilar y ejecutar la consulta.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md)   
 [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md)