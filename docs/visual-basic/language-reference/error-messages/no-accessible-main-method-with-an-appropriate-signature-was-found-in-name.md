---
title: No accesible &#39;Main&#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>No accesible &#39;Main&#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;
Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main` debe declararse como `Public Shared` si se ha definido en una clase o como `Public` si está definido en un módulo.  
  
 **Id. de error:** BC30737  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir una `Public Sub Main` procedimiento para el proyecto. Declara como `Shared` si y solo si se define dentro de una clase.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
