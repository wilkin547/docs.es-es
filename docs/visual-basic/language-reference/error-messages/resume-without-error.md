---
title: Reanudar sin error
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a>Reanudar sin error
Un `Resume` instrucción ha aparecido fuera del código de control de errores o el código salta en un controlador de errores, incluso si se ha producido ningún error.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Mover el `Resume` instrucción en un controlador de errores, o eliminarla.  
  
2.  Los saltos a etiquetas no se pueden realizar a través de procedimientos, de modo que busque el procedimiento para la etiqueta que identifica el controlador de errores. Si encuentra una etiqueta duplicada especificada como destino de un `GoTo` instrucción que no sea un `On Error GoTo` (instrucción), cambie la etiqueta de línea para que coincida con su destino pretendido.  
  
## <a name="see-also"></a>Vea también  
 [Resume (instrucción)](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
