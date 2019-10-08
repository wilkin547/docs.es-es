---
title: Procedimiento para usar procedimientos almacenados que toman parámetros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: e9d77cd1dc82e1b103c5f0d9f3f447ed105acaec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003245"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Procedimiento para usar procedimientos almacenados que toman parámetros
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asigna los parámetros de salida a parámetros de referencia y, para los tipos de valor, declara el parámetro como que acepta valores NULL.  
  
 Para obtener un ejemplo de cómo usar un parámetro de entrada en una consulta que devuelve un conjunto de filas, vea [How para: Devuelve conjuntos de filas @ no__t-0.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza un parámetro de entrada único (el identificador de cliente) y se devuelve un parámetro de salida (las ventas totales para ese cliente).  
  
```sql
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 La llamada a este procedimiento almacenado sería como sigue:  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos almacenados](stored-procedures.md)
- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Usar tipos de valor que aceptan valores NULL](../../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Tipos de valor que aceptan valores NULL](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
