---
description: 'Más información acerca de cómo: Mostrar LINQ to SQL comandos'
title: Procedimiento para mostrar comandos de LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: 480e7c1cbcceb09f0d727d03569d6277e0dd754b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785996"
---
# <a name="how-to-display-linq-to-sql-commands"></a>Procedimiento para mostrar comandos de LINQ to SQL

Utilice <xref:System.Data.Linq.DataContext.GetCommand%2A> para mostrar comandos SQL y otra información.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, la ventana de la consola muestra el resultado de la consulta, seguido de los comandos SQL que se generan, el tipo de los comandos y el tipo de la conexión.  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 El resultado se muestra de la manera siguiente:  
  
```console  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```console  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a>Vea también

- [Capacidad de depuración](debugging-support.md)
