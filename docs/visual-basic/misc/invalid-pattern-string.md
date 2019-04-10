---
title: Cadena de patrón no válida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298687"
---
# <a name="invalid-pattern-string"></a>Cadena de patrón no válida
La cadena de patrón especificada en la operación `Like` de una búsqueda no es válida.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Revise los caracteres válidos para las expresiones de lista.  
  
2. En el intervalo de patrones, asegúrese de que el carácter inicial del intervalo es menor que el carácter final del intervalo, como en `[a-z]`.  
  
3. En el intervalo de patrones, asegúrese de que no hay varios guiones uno junto a otro, como en `[a--z]`.  
  
4. Finalice los intervalos de patrones con un corchete de cierre.  
  
## <a name="see-also"></a>Vea también

- [Like (Operador)](../../visual-basic/language-reference/operators/like-operator.md)
