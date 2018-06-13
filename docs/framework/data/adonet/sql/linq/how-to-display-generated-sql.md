---
title: 'Cómo: Mostrar el código SQL generado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: edc0f8fea2768391a47e12940cbe083e41852f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361713"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="d88c7-102">Cómo: Mostrar el código SQL generado</span><span class="sxs-lookup"><span data-stu-id="d88c7-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="d88c7-103">Puede ver el código de SQL generado para las consultas y cambiar su procesamiento por medio de la propiedad <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="d88c7-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="d88c7-104">Este enfoque puede ser útil para entender la funcionalidad de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y para depurar problemas concretos.</span><span class="sxs-lookup"><span data-stu-id="d88c7-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d88c7-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d88c7-105">Example</span></span>  
 <span data-ttu-id="d88c7-106">En el ejemplo siguiente se utiliza la propiedad <xref:System.Data.Linq.DataContext.Log%2A> para mostrar el código de SQL en la ventana de la consola antes de que se ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="d88c7-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="d88c7-107">Puede utilizar esta propiedad con los comandos de consulta, inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="d88c7-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="d88c7-108">Las líneas de la ventana de consola son las que aparecen cuando se ejecuta el código de Visual Basic o C# siguiente.</span><span class="sxs-lookup"><span data-stu-id="d88c7-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d88c7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d88c7-109">See Also</span></span>  
 [<span data-ttu-id="d88c7-110">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="d88c7-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
