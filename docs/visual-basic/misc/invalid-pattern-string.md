---
title: Cadena de patrón no válida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: aa408f4cecc2a2774cb98cba96cd04a67afcc546
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402218"
---
# <a name="invalid-pattern-string"></a>Cadena de patrón no válida
La cadena de patrón especificada en la operación `Like` de una búsqueda no es válida.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Revise los caracteres válidos para las expresiones de lista.  
  
2. En el intervalo de patrones, asegúrese de que el carácter inicial del intervalo es menor que el carácter final del intervalo, como en `[a-z]`.  
  
3. En el intervalo de patrones, asegúrese de que no hay varios guiones uno junto a otro, como en `[a--z]`.  
  
4. Finalice los intervalos de patrones con un corchete de cierre.  
  
## <a name="see-also"></a>Consulte también

- [Like (operador)](../language-reference/operators/like-operator.md)
