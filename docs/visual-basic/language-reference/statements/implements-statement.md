---
title: Implements (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604216"
---
# <a name="implements-statement"></a>Implements (Instrucción)
Especifica uno o más interfaces, o miembros de interfaz que deben implementarse en la clase o definición de la estructura en la que aparece.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Elementos  
 `interfacename`  
 Requerido. Una interfaz cuyas propiedades, procedimientos y eventos deben implementarse por los miembros correspondientes de la clase o estructura.  
  
 `interfacemember`  
 Requerido. El miembro de interfaz que se está implementando.  
  
## <a name="remarks"></a>Comentarios  
 Una interfaz es una colección de prototipos que representan los miembros (propiedades, procedimientos y eventos) que encapsula la interfaz. Interfaces sólo contienen las declaraciones de miembros; las clases y estructuras implementan a estos miembros. Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 El `Implements` instrucción debe seguir inmediatamente el `Class` o `Structure` instrucción.  
  
 Cuando se implementa una interfaz, debe implementar todos los miembros declarados en la interfaz. Si se omite a cualquier miembro se considera un error de sintaxis. Para implementar un miembro individual, especifique la [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) palabra clave (que son independientes de la `Implements` instrucción) cuando se declara el miembro de la clase o estructura. Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Pueden utilizar las clases [privada](../../../visual-basic/language-reference/modifiers/private.md) las implementaciones de propiedades y procedimientos, pero estos miembros son accesibles solo para convertir una instancia de la clase que se implementa en una variable se declara como del tipo de la interfaz.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `Implements` instrucción para implementar miembros de una interfaz. Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento. La clase `customerInfo` implementa todos los miembros definidos en la interfaz.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Tenga en cuenta que la clase `customerInfo` utiliza la `Implements` instrucción en una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la `ICustomerInfo` interfaz. A continuación, todos los miembros de la clase usan el `Implements` palabra clave como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.  
  
## <a name="example"></a>Ejemplo  
 Los dos procedimientos siguientes muestran cómo puede usar la interfaz implementada en el ejemplo anterior. Para probar la implementación, agregue estos procedimientos en el proyecto y llame a la `testImplements` procedimiento.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
