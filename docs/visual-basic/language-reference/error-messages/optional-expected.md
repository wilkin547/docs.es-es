---
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 0ad0d0890b73103a0678b13409a24190329d37d4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266339"
---
# <a name="optional-expected"></a>Se esperaba 'Optional'
Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario. Cada argumento que sigue a un argumento opcional también debe ser opcional.  
  
 **Identificador de error:** BC30202  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si el argumento debe ser necesario, muévalo para que preceda al primer argumento opcional en la lista de argumentos.  
  
2.  Si el argumento está pensado para que sea opcional, use la `Optional` palabra clave.  
  
## <a name="see-also"></a>Vea también
- [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
