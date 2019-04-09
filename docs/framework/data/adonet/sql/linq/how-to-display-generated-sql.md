---
title: Filtrar para mostrar el código SQL generado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 8a69b3ae83d7f701428b3183f2b80e0d44a06537
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103628"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="8a272-102">Filtrar para mostrar el código SQL generado</span><span class="sxs-lookup"><span data-stu-id="8a272-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="8a272-103">Puede ver el código de SQL generado para las consultas y cambiar su procesamiento por medio de la propiedad <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a272-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="8a272-104">Este enfoque puede ser útil para entender la funcionalidad de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y para depurar problemas concretos.</span><span class="sxs-lookup"><span data-stu-id="8a272-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a272-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a272-105">Example</span></span>  
 <span data-ttu-id="8a272-106">En el ejemplo siguiente se utiliza la propiedad <xref:System.Data.Linq.DataContext.Log%2A> para mostrar el código de SQL en la ventana de la consola antes de que se ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="8a272-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="8a272-107">Puede utilizar esta propiedad con los comandos de consulta, inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="8a272-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="8a272-108">Las líneas de la ventana de consola son lo que ve cuando se ejecuta en Visual Basic o C# código que sigue.</span><span class="sxs-lookup"><span data-stu-id="8a272-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8a272-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a272-109">See also</span></span>

- [<span data-ttu-id="8a272-110">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="8a272-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
