---
description: 'Más información acerca de cómo: usar funciones de User-Defined de Scalar-Valued'
title: Procedimiento para usar funciones definidas por el usuario con valores escalares
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: e606dd3f840b8f082928217c6118b48d8d4a2e5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785815"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Procedimiento para usar funciones definidas por el usuario con valores escalares

Puede asignar un método de cliente definido en una clase a una función definida por el usuario utilizando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute>. Observe que el cuerpo del método construye una expresión que captura el intento de llamada al método y pasa esa expresión a <xref:System.Data.Linq.DataContext> para su conversión y ejecución.  
  
> [!NOTE]
> La ejecución directa sólo se produce si se llama a la función fuera de una consulta. Para obtener más información, consulte [Cómo: llamar a funciones insertadas de User-Defined](how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Ejemplo  

 El código de SQL siguiente presenta una función `ReverseCustName()` definida por el usuario con valores escalares.  
  
```sql  
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
