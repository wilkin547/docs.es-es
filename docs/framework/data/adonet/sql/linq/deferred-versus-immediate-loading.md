---
title: Carga inmediata y carga diferida
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
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 992d9a018f81bbd3f0c9204168f513024769e079
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deferred-versus-immediate-loading"></a>Carga inmediata y carga diferida
Al consultar un objeto, en realidad se recupera únicamente el objeto solicitado. El *relacionados* objetos no se capturan automáticamente al mismo tiempo. (Para obtener más información, consulte [consultas en varias relaciones](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) No hay forma de saber si los objetos relacionados están ya cargados, porque, si se intenta tener acceso a ellos, se genera una solicitud que los recupera.  
  
 Por ejemplo, quizás desee consultar un conjunto determinado de pedidos y después, sólo en algunas ocasiones, enviar una notificación por correo electrónico a determinados clientes. Inicialmente, no está obligado a recuperar todos los datos de clientes con todos los pedidos. Puede utilizar la carga aplazada para aplazar la recuperación de información adicional hasta que ésta no sea realmente necesaria. Considere el ejemplo siguiente:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 También podría darse el caso contrario. Es posible que una aplicación necesite ver al mismo tiempo los datos de los clientes y los pedidos. Sabe que necesita ambos conjuntos de datos. Sabe que su aplicación necesita información de los pedidos de cada cliente en cuanto obtiene los resultados. Seguramente no deseará enviar consultas individuales para los pedidos de cada cliente. Lo que realmente desea es recuperar los datos de pedidos junto con los clientes.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 También puede combinar clientes y pedidos en una consulta si forma el producto cruzado y recupera todos los elementos de datos relativos como una gran proyección. Sin embargo, estos resultados no son entidades. (Para obtener más información, consulte [el modelo de LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)). Las entidades son objetos que tienen identidad y que se pueden modificar, mientras que estos resultados serían proyecciones que no se pueden cambiar ni conservar. Lo que es peor, recuperaría una gran cantidad de datos redundantes, ya que cada cliente se repite para cada pedido en el resultado simplificado de la combinación.  
  
 Lo que realmente necesita es una manera de recuperar al mismo tiempo un conjunto de objetos relacionados. El conjunto es una sección delineada de un gráfico, de tal forma que nunca recuperaría más o menos de lo necesario para el uso previsto. Para este propósito, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona <xref:System.Data.Linq.DataLoadOptions> para la carga inmediata de una región de su modelo de objetos. Entre los métodos, se incluyen:  
  
-   El método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>, para cargar inmediatamente los datos relacionados con el destino principal.  
  
-   El método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>, para filtrar los objetos recuperados para una relación determinada.  
  
## <a name="see-also"></a>Vea también  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
