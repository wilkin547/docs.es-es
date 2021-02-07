---
description: 'Más información acerca de cómo: almacenar y reutilizar consultas'
title: Procedimiento para almacenar y reutilizar consultas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: a9c467cc9b2e39e6bd7616c6439d02c67f43d7c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738824"
---
# <a name="how-to-store-and-reuse-queries"></a>Procedimiento para almacenar y reutilizar consultas

Cuando una aplicación ejecuta muchas veces consultas que tienen una estructura similar, a menudo se mejora el rendimiento si se compila la consulta una vez y se ejecuta varias veces con parámetros diferentes. Por ejemplo, una aplicación podría tener que recuperar todos los clientes que están en una ciudad determinada, que es especificada por el usuario en un formulario en tiempo de ejecución. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite el uso de *consultas compiladas* para este propósito.  
  
> [!NOTE]
> Este patrón de utilización representa el uso más común de las consultas compiladas, pero también son posibles otros enfoques. Por ejemplo, las consultas compiladas se pueden almacenar como miembros estáticos en una clase parcial que extiende el código generado por el diseñador.  
  
## <a name="example"></a>Ejemplo  

 En muchos escenarios podrían reutilizarse las consultas entre límites de subprocesos. En tales casos, almacenar las consultas compiladas en variables estáticas es particularmente eficaz. En el ejemplo de código siguiente se da por supuesto que hay una clase `Queries` diseñada para almacenar las consultas compiladas y que hay una clase Northwind que representa un objeto <xref:System.Data.Linq.DataContext> fuertemente tipado.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>Ejemplo  

 Actualmente no se pueden almacenar (en variables estáticas) consultas que devuelven un *tipo anónimo*, porque el tipo no tiene ningún nombre que proporcionar como argumento genérico. En el ejemplo siguiente se muestra cómo se puede solucionar el problema creando un tipo que pueda representar el resultado y, a continuación, cómo se utiliza como argumento genérico.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.Linq.CompiledQuery>
- [Conceptos sobre consultas](query-concepts.md)
- [Consultar la base de datos](querying-the-database.md)
