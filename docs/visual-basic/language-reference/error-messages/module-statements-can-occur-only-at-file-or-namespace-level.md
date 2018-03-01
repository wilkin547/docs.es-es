---
title: "&#39; Módulo &#39; las instrucciones pueden ocurrir en el nivel de archivo o espacio de nombres"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61fe12fbd7d20e6cd2b6bc464e7fc3293150213b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39; Módulo &#39; las instrucciones pueden ocurrir en el nivel de archivo o espacio de nombres
`Module`las instrucciones deben aparecer en la parte superior del archivo de origen inmediatamente después de `Option` y `Imports` instrucciones, los atributos globales y declaraciones de espacios de nombres, pero antes de todas las demás declaraciones.  
  
 **Id. de error:** BC30617  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mover el `Module` instrucción al principio de su archivo de origen o de declaración de espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
