---
description: 'Más información sobre: Implements (instrucción)'
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
ms.openlocfilehash: aa53d1f3b4ba9d9111f5ffb09198a11511f8d9e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768992"
---
# <a name="implements-statement"></a>Implements (Instrucción)

Especifica una o más interfaces, o miembros de interfaz, que se deben implementar en la definición de clase o estructura en la que aparece.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Partes  

 `interfacename`  
 Necesario. Interfaz cuyas propiedades, procedimientos y eventos van a ser implementados por los miembros correspondientes de la clase o estructura.  
  
 `interfacemember`  
 Necesario. Miembro de una interfaz que se está implementando.  
  
## <a name="remarks"></a>Observaciones  

 Una interfaz es una colección de prototipos que representan los miembros (propiedades, procedimientos y eventos) que la interfaz encapsula. Las interfaces contienen solo las declaraciones de los miembros; las clases y estructuras implementan estos miembros. Para obtener más información, vea [Interfaces](../../programming-guide/language-features/interfaces/index.md).  
  
 La `Implements` instrucción debe seguir inmediatamente a `Class` la `Structure` instrucción o.  
  
 Al implementar una interfaz, debe implementar todos los miembros declarados en la interfaz. Omitir cualquier miembro se considera un error de sintaxis. Para implementar un miembro individual, se especifica la palabra clave [Implements](implements-clause.md) (que es independiente de la `Implements` instrucción) cuando se declara el miembro en la clase o estructura. Para obtener más información, vea [Interfaces](../../programming-guide/language-features/interfaces/index.md).  
  
 Las clases pueden utilizar implementaciones [privadas](../modifiers/private.md) de propiedades y procedimientos, pero solo se puede tener acceso a estos miembros si se convierte una instancia de la clase de implementación en una variable declarada como del tipo de la interfaz.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo utilizar la `Implements` instrucción para implementar miembros de una interfaz. Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento. La clase `customerInfo` implementa todos los miembros definidos en la interfaz.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Tenga en cuenta que la clase `customerInfo` utiliza la `Implements` instrucción en una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la `ICustomerInfo` interfaz. Después, cada miembro de la clase usa la `Implements` palabra clave como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.  
  
## <a name="example"></a>Ejemplo  

 Los dos procedimientos siguientes muestran cómo podría usar la interfaz implementada en el ejemplo anterior. Para probar la implementación, agregue estos procedimientos al proyecto y llame al `testImplements` procedimiento.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vea también

- [Implementaciones](implements-clause.md)
- [Instrucción Interface](interface-statement.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
