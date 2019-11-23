---
title: 'Cómo: Usar funciones escalares definidas por el usuario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: dfe82fd50eb3eedeaff9082a4288901f72197795
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003235"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Cómo: Usar funciones escalares definidas por el usuario
Puede asignar un método de cliente definido en una clase a una función definida por el usuario utilizando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute>. Observe que el cuerpo del método construye una expresión que captura el intento de llamada al método y pasa esa expresión a <xref:System.Data.Linq.DataContext> para su conversión y ejecución.  
  
> [!NOTE]
> La ejecución directa sólo se produce si se llama a la función fuera de una consulta. Para obtener más información, vea [Cómo: llamar a funciones insertadas definidas por el usuario](how-to-call-user-defined-functions-inline.md).  
  
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
