---
title: '&#39;Módulo&#39; instrucciones pueden ocurrir solo en el nivel de archivo o espacio de nombres'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;Módulo&#39; instrucciones pueden ocurrir solo en el nivel de archivo o espacio de nombres
`Module` las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y declaraciones de espacios de nombres, pero antes de todas las demás declaraciones.  
  
 **Id. de error:** BC30617  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mover el `Module` instrucción al principio de su archivo de origen o de declaración de espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
