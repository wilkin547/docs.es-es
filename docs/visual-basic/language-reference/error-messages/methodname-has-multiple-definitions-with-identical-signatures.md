---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 97113227591c40f302d3d1a08a4248a8199817bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285433"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a>'\<methodname >' tiene varias definiciones con firmas idénticas
Un `Function` o `Sub` declaración de procedimiento utiliza el procedimiento idéntico nombre y lista de argumentos que una declaración anterior. Una posible causa es un intento de sobrecargar el procedimiento original. Los procedimientos sobrecargados deben tener distintas listas de argumentos.  
  
 **Identificador de error:** BC30269  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nombre del procedimiento o la lista de argumentos, o quite la declaración duplicada.  
  
## <a name="see-also"></a>Vea también
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Consideraciones sobre la sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
