---
title: Tipo de &#39; &lt;typename&gt;&#39; no tiene constructores
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d2c1bfcc4af928fff6a10ca3d97957e75cbd7355
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-39lttypenamegt39-has-no-constructors"></a>Tipo de &#39; &lt;typename&gt;&#39; no tiene constructores
Un tipo no admite una llamada a `Sub New()`. Una causa probable puede ser un archivo binario o un compilador dañado.  
  
 **Id. de error:** BC30251  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si el tipo está en proyecto distinto o en un archivo al que se hace referencia, reinstale el proyecto o archivo en cuestión.  
  
2.  Si el tipo se encuentra en el mismo proyecto, vuelva a compilar el ensamblado que contiene dicho tipo.  
  
3.  Si el error se repite, reinstale el compilador de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
4.  Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Hable con nosotros](/visualstudio/ide/talk-to-us)
