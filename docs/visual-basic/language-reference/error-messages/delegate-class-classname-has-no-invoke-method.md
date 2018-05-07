---
title: Clase delegada &#39; &lt;classname&gt; &#39; no tiene ningún método Invoke y, por lo que una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Clase delegada &#39; &lt;classname&gt; &#39; no tiene ningún método Invoke y, por lo que una expresión de este tipo no puede ser el destino de una llamada a método
Una llamada a `Invoke` a través de un delegado error porque `Invoke` no está implementada en la clase de delegado.  
  
 **Id. de error:** BC30220  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que se ha creado una instancia de la clase de delegado con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.  
  
2.  Busque el código que implementa la clase de delegado y asegúrese de que implementa el `Invoke` procedimiento.  
  
## <a name="see-also"></a>Vea también  
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
