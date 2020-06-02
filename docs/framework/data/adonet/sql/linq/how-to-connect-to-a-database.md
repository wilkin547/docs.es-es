---
title: Procedimiento para conectar a una base de datos
description: Aprenda a usar DataContext para conectarse a una base de datos en LINQ to SQL. Consulte estos ejemplos para usar DataContext para conectarse a una base de datos y obtener filas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: c3320a598cb8407ab584530c615c2e5ef0de53c8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286409"
---
# <a name="how-to-connect-to-a-database"></a>Procedimiento para conectar a una base de datos
<xref:System.Data.Linq.DataContext> es la canalización principal mediante la cual se conecta a una base de datos, recupera los objetos de ella y le vuelve a enviar los cambios. Puede usar el <xref:System.Data.Linq.DataContext> mismo modo que usaría un ADO.net <xref:System.Data.SqlClient.SqlConnection> . De hecho, <xref:System.Data.Linq.DataContext> se inicializa con la conexión o cadena de conexión que proporcione. Para obtener más información, vea [métodos DataContext (Object](/visualstudio/data-tools/datacontext-methods-o-r-designer)Relational Designer).  
  
 El propósito de <xref:System.Data.Linq.DataContext> es convertir sus solicitudes de objetos en consultas SQL que se van a ejecutar en la base de datos y, a continuación, ensamblar los objetos a partir de los resultados. <xref:System.Data.Linq.DataContext>Habilita la consulta Language-Integrated Query (LINQ) implementando el mismo patrón de operador que los operadores de consulta estándar, como `Where` y `Select` .  
  
> [!IMPORTANT]
> Es fundamental mantener una conexión segura. Para obtener más información, consulte [seguridad en LINQ to SQL](security-in-linq-to-sql.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se utiliza <xref:System.Data.Linq.DataContext> para establecer una conexión con la base de datos de ejemplo Northwind y recuperar las filas de clientes cuya ciudad es Londres (London).  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 Cada tabla de base de datos se representa como una colección `Table` disponible a través del método <xref:System.Data.Linq.DataContext.GetTable%2A>, utilizando la clase de entidad para su identificación.  
  
## <a name="example"></a>Ejemplo  
 El procedimiento recomendado es declarar un <xref:System.Data.Linq.DataContext> fuertemente tipado en lugar de confiar en la clase <xref:System.Data.Linq.DataContext> básica y el método <xref:System.Data.Linq.DataContext.GetTable%2A>. Un <xref:System.Data.Linq.DataContext> fuertemente tipado declara todas las colecciones `Table` como miembros del contexto, como en el ejemplo siguiente.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 Después, puede expresar la consulta de clientes de Londres de manera más sencilla:  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Consulte también

- [Comunicarse con la base de datos](communicating-with-the-database.md)
