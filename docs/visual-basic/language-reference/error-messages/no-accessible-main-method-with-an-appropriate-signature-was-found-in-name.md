---
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: b3aa66416f0cad6a6fb29a20aa0bca5e3486a18e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275436"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>No se encontró ningún método 'Main' accesible con una firma apropiada en '\<nombre >'
Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main` debe declararse como `Public Shared` si está definido en una clase o como `Public` si está definido en un módulo.  
  
 **Identificador de error:** BC30737  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir un `Public Sub Main` procedimiento para el proyecto. Declara como `Shared` si y solo si se define dentro de una clase.  
  
## <a name="see-also"></a>Vea también
- [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
