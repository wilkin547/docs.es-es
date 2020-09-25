---
title: Funciones canónicas bit a bit
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 67ae0302f6faf0fb7284bc0c4a53a90ba6d55e08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185267"
---
# <a name="bitwise-canonical-functions"></a>Funciones canónicas bit a bit

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] incluye funciones canónicas bit a bit.  
  
## <a name="remarks"></a>Observaciones  

 En la tabla siguiente se muestran las demás funciones canónicas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bit a bit. Estas funciones devolverán `Null` si `Null` se proporciona la entrada. El tipo de valor devuelto de las funciones es igual que los tipos de argumento. Los argumentos deben ser del mismo tipo, si la función toma más de uno. Para realizar las operaciones bit a bit a través de tipos diferentes, es necesario convertir explícitamente al mismo tipo.  
  
|Función|Descripción|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Devuelve la conjunción bit a bit de `value1` y `value2` como el tipo de `value1` y `value2`.<br /><br /> **Argumentos**<br /><br /> , `Byte` , `Int16` `Int32` Y `Int64` .<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Devuelve la negación bit a bit de `value`.<br /><br /> **Argumentos**<br /><br /> , `Byte` , `Int16` `Int32` Y `Int64` .<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Devuelve la disyunción bit a bit de `value1` y `value2` como el tipo de `value1` y `value2`.<br /><br /> **Argumentos**<br /><br /> `Byte`, `Int16` `Int32` Y `Int64` .<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Devuelve la disyunción exclusiva bit a bit de `value1` y `value2` como el tipo de `value1` y `value2`.<br /><br /> **Argumentos**<br /><br /> `Byte`, `Int16` `Int32` Y `Int64` .<br /><br /> **Ejemplo**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Consulte también

- [Funciones canónicas](canonical-functions.md)
