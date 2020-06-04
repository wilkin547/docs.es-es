---
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6760b931ceb2ad5c2c04169d664da8629badc487
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409418"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>No se encontró ningún método 'Main' accesible con una firma apropiada en '\<name>'
Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main`se debe declarar como `Public Shared` si se hubiera definido en una clase o como si se hubiera `Public` definido en un módulo.  
  
 **Identificador de error:** BC30737  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Defina un `Public Sub Main` procedimiento para el proyecto. Declárela como `Shared` si y solo si lo define dentro de una clase.  
  
## <a name="see-also"></a>Consulte también

- [Estructura de un programa de Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
