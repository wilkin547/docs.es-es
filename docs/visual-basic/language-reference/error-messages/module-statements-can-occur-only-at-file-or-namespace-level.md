---
title: Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bf0239422fb5a98e4670aea407f684753d3a7ea4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825448"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Las instrucciones 'Module' sólo pueden ocurrir en el nivel de archivo o de espacio de nombres
`Module` las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y las declaraciones de espacio de nombres, pero antes de todas las demás declaraciones.  
  
 **Identificador de error:** BC30617  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mueva la instrucción `Module` a la parte superior de la declaración del espacio de nombres o el archivo de código fuente.  
  
## <a name="see-also"></a>Vea también

- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
