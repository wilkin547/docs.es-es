---
description: "Más información acerca de: BC30737: no se encontró ningún método ' Main ' accesible con una firma apropiada en '<name>"
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 1865d6baea824c435d276aa9c160bcd282abf4ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795656"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>BC30737: no se encontró ningún método ' Main ' accesible con una signatura adecuada en ' \<name> '

Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main` se debe declarar como `Public Shared` si se hubiera definido en una clase o como si se hubiera `Public` definido en un módulo.

 **Identificador de error:** BC30737

## <a name="to-correct-this-error"></a>Para corregir este error

- Defina un `Public Sub Main` procedimiento para el proyecto. Declárela como `Shared` si y solo si lo define dentro de una clase.

## <a name="see-also"></a>Vea también

- [Estructura de un programa de Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
