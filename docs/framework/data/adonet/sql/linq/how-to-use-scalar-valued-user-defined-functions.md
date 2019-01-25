---
title: Procedimiento Utilice las funciones escalares de definido por el usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: 33c6ae89184b90ba69cc9c3c01f0b1ec9d7ff1cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661690"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="5eea3-102">Procedimiento Utilice las funciones escalares de definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="5eea3-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="5eea3-103">Puede asignar un método de cliente definido en una clase a una función definida por el usuario utilizando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5eea3-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="5eea3-104">Observe que el cuerpo del método construye una expresión que captura el intento de llamada al método y pasa esa expresión a <xref:System.Data.Linq.DataContext> para su conversión y ejecución.</span><span class="sxs-lookup"><span data-stu-id="5eea3-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5eea3-105">La ejecución directa sólo se produce si se llama a la función fuera de una consulta.</span><span class="sxs-lookup"><span data-stu-id="5eea3-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="5eea3-106">Para obtener más información, vea [Cómo: Llamar a funciones definidas por el usuario alineadas](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span><span class="sxs-lookup"><span data-stu-id="5eea3-106">For more information, see [How to: Call User-Defined Functions Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eea3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5eea3-107">Example</span></span>  
 <span data-ttu-id="5eea3-108">El código de SQL siguiente presenta una función `ReverseCustName()` definida por el usuario con valores escalares.</span><span class="sxs-lookup"><span data-stu-id="5eea3-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="5eea3-109">Para este código, asignaría un método de cliente como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5eea3-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5eea3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eea3-110">See also</span></span>
- [<span data-ttu-id="5eea3-111">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="5eea3-111">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
