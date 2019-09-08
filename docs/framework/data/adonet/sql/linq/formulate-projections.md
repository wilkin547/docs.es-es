---
title: Formular proyecciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793819"
---
# <a name="formulate-projections"></a>Formular proyecciones
En los siguientes ejemplos se muestra `select` cómo la C# instrucción `Select` in y la instrucción de Visual Basic pueden combinarse con otras características para formar proyecciones de consulta.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) para devolver una secuencia de nombres `Customers`de contacto para.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver una secuencia de nombres de `Customers`contacto y números de teléfono para.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver una secuencia de nombres y números de teléfono de los empleados. Los `FirstName` campos `LastName` y se combinan en un único campo (`Name` `Phone` ) y el nombre `HomePhone` del campo en la secuencia resultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver `ProductID`una secuencia de todos los objetos `HalfPrice`y un valor calculado denominado. Este valor se establece en `UnitPrice` dividido entre 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select` usa la cláusula en`select` Visual Basic ( C#cláusula en) y una *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad del producto.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza `Select` una cláusula`select` de Visual Basic C#(cláusula en) y un *tipo conocido* (nombre) para devolver una secuencia de los nombres de los empleados.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `Select` se `Where` usa y en`select` Visual Basic `where` ( C#y en) para devolver una *secuencia filtrada* de nombres de contacto para los clientes de Londres.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select` utiliza una cláusula en`select` Visual Basic ( C#cláusula en) y los *tipos anónimos* para devolver un *subconjunto con forma* de los datos sobre los clientes.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:  
  
- Una secuencia de todos los pedidos y sus `OrderID` correspondientes.  
  
- Una subsecuencia de los elementos del pedido que tienen descuento.  
  
- La cantidad de dinero que se ahorra si no se incluye el envío en el precio.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de consultas](query-examples.md)
