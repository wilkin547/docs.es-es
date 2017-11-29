---
title: '&#39; &lt;typename&gt;&#39; es un tipo delegado'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords: BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39; &lt;typename&gt;&#39; es un tipo delegado
'\<typename >' es un tipo de delegado. Construcción de delegado permite una única expresión AddressOf como una lista de argumentos. A menudo se puede utilizar una expresión AddressOf en lugar de una construcción de delegado.  
  
 Un `New` cláusula que crea una instancia de una clase de delegado proporciona una lista de argumentos no válido al constructor de delegado.  
  
 Puede proporcionar un solo `AddressOf` expresión al crear una nueva instancia de delegado.  
  
 Este error puede producirse si no pasa ningún argumento al constructor de delegado, si se pasa más de un argumento, o si se pasa un argumento único que no es válido `AddressOf` expresión.  
  
 **Id. de error:** BC32008  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Usar un solo `AddressOf` expresión en la lista de argumentos para la clase de delegado en el `New` cláusula.  
  
## <a name="see-also"></a>Vea también  
 [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md)  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Invocar un método delegado](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
