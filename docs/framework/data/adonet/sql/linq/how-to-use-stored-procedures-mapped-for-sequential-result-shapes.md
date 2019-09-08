---
title: Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: bae10e823a274304f21292cf55947a4d4eaccc10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781457"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados. Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos. Para obtener más información, consulte [Cómo Usar procedimientos almacenados asignados para varias formas](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)de resultados.  
  
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

- [Procedimientos almacenados](stored-procedures.md)
