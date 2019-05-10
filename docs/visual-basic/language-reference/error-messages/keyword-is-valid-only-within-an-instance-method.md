---
title: "'<keyword>' sólo es válida en un método de instancia"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 8ec1e704815ee10cb98d8cc20fb5982ee4b92832
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662011"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<palabra clave >' es válido solo dentro de un método de instancia
El `Me`, `MyClass`, y `MyBase` palabras clave que hacen referencia a instancias de clase específica. No se pueden utilizar dentro de un compartido `Function` o `Sub` procedimiento.  
  
 **Identificador de error:** BC30043  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.  
  
## <a name="see-also"></a>Vea también

- [Asignación de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
