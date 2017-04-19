---
title: "Clase delegada&lt;classname&gt;&quot; no tiene ningún método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ddc5ef0f0b3e9baa58f17dafb727e250c0fba9fd
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Clase delegada&lt;classname&gt;' no tiene ningún método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método
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
