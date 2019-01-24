---
title: '&#39;Opcional&#39; esperado'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 46bd84e2bcf5c5bea11a5c9d8b6e9254c49e3021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642482"
---
# <a name="39optional39-expected"></a>&#39;Opcional&#39; esperado
Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario. Cada argumento que sigue a un argumento opcional también debe ser opcional.  
  
 **Identificador de error:** BC30202  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si el argumento debe ser necesario, muévalo para que preceda al primer argumento opcional en la lista de argumentos.  
  
2.  Si el argumento está pensado para que sea opcional, use la `Optional` palabra clave.  
  
## <a name="see-also"></a>Vea también
- [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
