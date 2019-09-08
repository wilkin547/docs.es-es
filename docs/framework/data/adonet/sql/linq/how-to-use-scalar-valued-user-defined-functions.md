---
title: Procedimiento para usar funciones definidas por el usuario con valores escalares
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: da4e5e8fe4682191a0c8e2b0ce6a7b945fe63deb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781477"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Procedimiento para usar funciones definidas por el usuario con valores escalares
Puede asignar un método de cliente definido en una clase a una función definida por el usuario utilizando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute>. Observe que el cuerpo del método construye una expresión que captura el intento de llamada al método y pasa esa expresión a <xref:System.Data.Linq.DataContext> para su conversión y ejecución.  
  
> [!NOTE]
> La ejecución directa sólo se produce si se llama a la función fuera de una consulta. Para obtener más información, consulte [Cómo Llamar a funciones alineadas](how-to-call-user-defined-functions-inline.md)definidas por el usuario.  
  
## <a name="example"></a>Ejemplo  
 El código de SQL siguiente presenta una función `ReverseCustName()` definida por el usuario con valores escalares.  
  
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
  
 Para este código, asignaría un método de cliente como el siguiente:  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Funciones definidas por el usuario](user-defined-functions.md)
