---
title: '&quot;&lt;typename&gt;&quot; es un tipo delegado | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
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
ms.openlocfilehash: 3d6cc283f7e9815eb9b723a450731998f14b3424
ms.lasthandoff: 03/13/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>'&lt;typename&gt;' es un tipo delegado
'\<typename >' es un tipo delegado. Construcción de delegado permite una única expresión AddressOf como una lista de argumentos. A menudo la expresión AddressOf puede utilizarse en lugar de una construcción de delegado.  
  
 Un `New` cláusula que crea una instancia de una clase de delegado proporciona una lista de argumentos no válido al constructor del delegado.  
  
 Puede proporcionar una sola `AddressOf` expresión cuando se crea una nueva instancia de delegado.  
  
 Este error puede producirse si no pasa ningún argumento al constructor de delegado, si se pasa más de un argumento, o si se pasa un único argumento que no es válido `AddressOf` expresión.  
  
 **Id. de error:** BC32008  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Usar una sola `AddressOf` expresión en la lista de argumentos para la clase de delegado en el `New` cláusula.  
  
## <a name="see-also"></a>Vea también  
 [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md)   
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Invocar un método delegado](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
