---
title: Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: 8378a175ab2479ab9769ca08579e1c89269eaba4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003220"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados. Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos. Para obtener más información, vea [Cómo: Use procedimientos almacenados asignados para varias formas de resultados @ no__t-0.  
  
## <a name="example"></a>Ejemplo  
 A continuación se muestra el código T-SQL de un procedimiento almacenado que devuelve varias formas de resultados secuencialmente:  
  
```sql
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
