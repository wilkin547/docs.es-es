---
title: "Realizar una subconsulta en una operación de agrupación"
description: "Cómo realizar una subconsulta en una operación de agrupación."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c2c95479db10d81e748349e156f2314a6d4fccf
ms.lasthandoff: 03/13/2017

---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Realizar una subconsulta en una operación de agrupación

En este tema se muestran dos maneras diferentes de crear una consulta que ordena los datos de origen en grupos y, luego, realiza una subconsulta en cada grupo individualmente. La técnica básica de cada ejemplo consiste en agrupar los elementos de origen usando una *continuación* denominada `newGroup` y después generar una nueva subconsulta en `newGroup`. Esta subconsulta se ejecuta en cada uno de los nuevos grupos creados por la consulta externa. Tenga en cuenta que en este ejemplo concreto el resultado final no es un grupo, sino una secuencia plana de tipos anónimos.  
  
 Para obtener más información sobre cómo agrupar, consulte [group clause](../language-reference/keywords/group-clause.md) (Cláusula group).  
  
 Para obtener más información sobre continuaciones, consulte [into](../language-reference/keywords/into.md). En el ejemplo siguiente se usa una estructura de datos en memoria como origen de datos, pero se aplican los mismos principios para cualquier tipo de origen de datos LINQ.  
  
## <a name="example"></a>Ejemplo 

 > [!NOTE]
 > Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos).

 [!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)
