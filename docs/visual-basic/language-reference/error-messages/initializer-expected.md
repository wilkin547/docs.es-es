---
title: Se esperaba un inicializador
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a>Se esperaba un inicializador
Ha intentado declarar una instancia de una clase mediante un inicializador de objeto en el que la lista de inicializaciones está vacía, tal como se muestra en el ejemplo siguiente.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Al menos un campo o una propiedad se debe inicializar en la lista de inicializadores, como se muestra en el ejemplo siguiente.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Id. de error:** BC30996  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Inicializar al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.  
  
## <a name="see-also"></a>Vea también  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
