---
title: No accesible &#39;Main&#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501495"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>No accesible &#39;Main&#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;
Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main` debe declararse como `Public Shared` si está definido en una clase o como `Public` si está definido en un módulo.  
  
 **Identificador de error:** BC30737  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir un `Public Sub Main` procedimiento para el proyecto. Declara como `Shared` si y solo si se define dentro de una clase.  
  
## <a name="see-also"></a>Vea también
- [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
