---
title: "Cómo: Usar procedimientos almacenados asignados en varias formas de resultados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fde4dd9044ff2bc6d781d7ceafec2bde3df7e14d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Cómo: Usar procedimientos almacenados asignados en varias formas de resultados
Cuando un procedimiento almacenado puede devolver varias formas de resultados, el tipo de valor devuelto no puede estar fuertemente tipado para una forma de proyección única. Aunque [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede generar todos los tipos de proyección posibles, no puede saber el orden en el que se devolverá.  
  
 Compare este escenario con los procedimientos almacenados que generan varias formas de resultados secuencialmente. Para obtener más información, consulte [Cómo: Use almacenado asignado procedimientos para formas de resultados secuenciales](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).  
  
 El atributo <xref:System.Data.Linq.Mapping.ResultTypeAttribute> se aplica a los procedimientos almacenados que devuelven varios tipos de resultados para especificar el conjunto de tipos que el procedimiento puede devolver.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de código SQL, la forma del resultado depende de la entrada (`shape =1` o `shape = 2`). No se sabe qué proyección se devolverá primero.  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 Usaría código similar al siguiente para ejecutar este procedimiento almacenado.  
  
> [!NOTE]
>  Debe utilizar el patrón <xref:System.Data.Linq.IMultipleResults.GetResult%2A> para obtener un enumerador del tipo correcto, basado en su conocimiento del procedimiento almacenado.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
