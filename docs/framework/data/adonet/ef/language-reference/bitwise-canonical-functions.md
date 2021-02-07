---
description: 'Más información sobre: funciones canónicas bit a bit'
title: Funciones canónicas bit a bit
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: a811c707749af2d2fa9472ae2d1444c3f076aeec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697106"
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
  
## <a name="see-also"></a>Vea también

- [Funciones canónicas](canonical-functions.md)
