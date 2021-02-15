---
description: 'Más información acerca de: cadena de patrón no válida'
title: Cadena de patrón no válida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4fbf16dd43ac4ae44e1a99d85caae4a7baf99109
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462066"
---
# <a name="invalid-pattern-string"></a>Cadena de patrón no válida

La cadena de patrón especificada en la operación `Like` de una búsqueda no es válida.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Revise los caracteres válidos para las expresiones de lista.  
  
2. En el intervalo de patrones, asegúrese de que el carácter inicial del intervalo es menor que el carácter final del intervalo, como en `[a-z]`.  
  
3. En el intervalo de patrones, asegúrese de que no hay varios guiones uno junto a otro, como en `[a--z]`.  
  
4. Finalice los intervalos de patrones con un corchete de cierre.  
  
## <a name="see-also"></a>Consulte también

- [Like (Operador)](../language-reference/operators/like-operator.md)
