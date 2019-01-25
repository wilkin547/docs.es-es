---
title: Procedimiento Usar procedimientos almacenados asignados en formas de resultados secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: 296870029d2329640466b3a540e9057738173aa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495661"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Procedimiento Usar procedimientos almacenados asignados en formas de resultados secuenciales
Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados. Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos. Para obtener más información, vea [Cómo: Usar procedimientos almacenados asignados en varias formas de resultados](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).  
  
## <a name="example"></a>Ejemplo  
 A continuación se muestra el código T-SQL de un procedimiento almacenado que devuelve varias formas de resultados secuencialmente:  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 Usaría código similar al siguiente para ejecutar este procedimiento almacenado.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Vea también
- [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
