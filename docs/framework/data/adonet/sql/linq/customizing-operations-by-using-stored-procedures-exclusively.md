---
description: Obtener más información acerca de cómo personalizar las operaciones mediante procedimientos almacenados exclusivamente
title: Personalizar operaciones utilizando exclusivamente procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 4ddcc6b4face1abccb502e12617105a734bb5f0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729554"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="95ccd-103">Personalizar operaciones utilizando exclusivamente procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="95ccd-103">Customizing Operations by Using Stored Procedures Exclusively</span></span>

<span data-ttu-id="95ccd-104">Un escenario común es obtener acceso a los datos utilizando únicamente procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="95ccd-104">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95ccd-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95ccd-105">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="95ccd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="95ccd-106">Description</span></span>  

 <span data-ttu-id="95ccd-107">Puede modificar el ejemplo que se proporciona en la [Personalización de operaciones utilizando procedimientos almacenados](customizing-operations-by-using-stored-procedures.md) reemplazando incluso la primera consulta (que provoca la ejecución dinámica de SQL) con una llamada al método que contiene un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="95ccd-107">You can modify the example provided in [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="95ccd-108">Supongamos que `CustomersByCity` es el método, como en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="95ccd-108">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="95ccd-109">Código</span><span class="sxs-lookup"><span data-stu-id="95ccd-109">Code</span></span>  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="95ccd-110">El código siguiente se ejecuta sin SQL dinámico.</span><span class="sxs-lookup"><span data-stu-id="95ccd-110">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="95ccd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="95ccd-111">See also</span></span>

- [<span data-ttu-id="95ccd-112">Responsabilidades del desarrollador al invalidar un comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="95ccd-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)
