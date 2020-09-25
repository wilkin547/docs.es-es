---
title: Formular proyecciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f0bc6dfcff7778ebc7156cbb039e13570c90467b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194406"
---
# <a name="formulate-projections"></a>Formular proyecciones

En los siguientes ejemplos se muestra cómo la `select` instrucción en C# y la `Select` instrucción de Visual Basic se pueden combinar con otras características para formar proyecciones de consulta.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) para devolver una secuencia de nombres de contacto para `Customers` .  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y los *tipos anónimos* para devolver una secuencia de nombres de contacto y números de teléfono para `Customers` .  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y los *tipos anónimos* para devolver una secuencia de nombres y números de teléfono de los empleados. Los `FirstName` `LastName` campos y se combinan en un único campo ( `Name` ) y el `HomePhone` nombre del campo `Phone` en la secuencia resultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y los *tipos anónimos* para devolver una secuencia de todos los objetos `ProductID` y un valor calculado denominado `HalfPrice` . Este valor se establece en `UnitPrice` dividido entre 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `Select` cláusula en Visual Basic ( `select` cláusula en C#) y una *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad del producto.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza una `Select` cláusula Visual Basic ( `select` cláusula en C#) y un *tipo conocido* (nombre) para devolver una secuencia de los nombres de los empleados.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente `Select` se usa y `Where` en Visual Basic ( `select` y `where` en C#) para devolver una *secuencia filtrada* de nombres de contacto para los clientes de Londres.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza una `Select` cláusula en Visual Basic ( `select` cláusula en C#) y *tipos anónimos* para devolver un *subconjunto con forma* de los datos sobre los clientes.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:  
  
- Una secuencia de todos los pedidos y sus `OrderID` correspondientes.  
  
- Una subsecuencia de los elementos del pedido que tienen descuento.  
  
- La cantidad de dinero que se ahorra si no se incluye el envío en el precio.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de consultas](query-examples.md)
