---
title: Personalizar operaciones utilizando exclusivamente procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 61230ffc5cd055ee64de9d519cdfb4d76c856ca3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128653"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="6da88-102">Personalizar operaciones utilizando exclusivamente procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="6da88-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="6da88-103">Un escenario común es obtener acceso a los datos utilizando únicamente procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="6da88-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6da88-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6da88-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6da88-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="6da88-105">Description</span></span>  
 <span data-ttu-id="6da88-106">Puede modificar el ejemplo proporcionado en [personalizar operaciones utilizando procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) reemplazando incluso la primera consulta (que hace que la ejecución de SQL dinámica) con una llamada al método que contiene un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="6da88-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="6da88-107">Supongamos que `CustomersByCity` es el método, como en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6da88-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6da88-108">Código</span><span class="sxs-lookup"><span data-stu-id="6da88-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="6da88-109">El código siguiente se ejecuta sin SQL dinámico.</span><span class="sxs-lookup"><span data-stu-id="6da88-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="6da88-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6da88-110">See also</span></span>

- [<span data-ttu-id="6da88-111">Responsabilidades del desarrollador al invalidar un comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="6da88-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
