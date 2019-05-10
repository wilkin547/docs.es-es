---
title: No se encontró ningún método 'Main' accesible con una firma apropiada en '<name>'
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 559c905d1e2e2de4500771a93d6116f9630011ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591970"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>No se encontró ningún método 'Main' accesible con una firma apropiada en '\<nombre >'
Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main` debe declararse como `Public Shared` si está definido en una clase o como `Public` si está definido en un módulo.  
  
 **Identificador de error:** BC30737  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Definir un `Public Sub Main` procedimiento para el proyecto. Declara como `Shared` si y solo si se define dentro de una clase.  
  
## <a name="see-also"></a>Vea también

- [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
