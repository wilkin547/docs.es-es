---
title: '&#39;&lt;MethodName&gt; &#39; tiene varias definiciones con firmas idénticas'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: daa1bc4fcc3ee0fe0279a029f9aac03d4555d582
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536950"
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a>&#39;&lt;MethodName&gt; &#39; tiene varias definiciones con firmas idénticas
Un `Function` o `Sub` declaración de procedimiento utiliza el procedimiento idéntico nombre y lista de argumentos que una declaración anterior. Una posible causa es un intento de sobrecargar el procedimiento original. Los procedimientos sobrecargados deben tener distintas listas de argumentos.  
  
 **Identificador de error:** BC30269  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nombre del procedimiento o la lista de argumentos, o quite la declaración duplicada.  
  
## <a name="see-also"></a>Vea también
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Consideraciones sobre la sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
