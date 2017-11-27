---
title: "El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords: BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c986fcf188482c526c53ddf3019cec5163d0b62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
Un elemento de programación que toma uno o más argumentos que se incluye en una consulta LINQ. El compilador es no puede inferir una variable de rango de ese elemento de programación.  
  
 **Id. de error:** BC36599  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Proporcione un nombre de variable explícito para el elemento de programación, como se muestra en el código siguiente:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
