---
title: Directivas de Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8219f17f1b8093b4d02b370c7b008101923b1873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="directives-visual-basic"></a>Directivas de Visual Basic
Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.  
  
## <a name="in-this-section"></a>En esta sección  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md) : definir una constante del compilador  
  
 [#ExternalSource (directiva)](../../../visual-basic/language-reference/directives/externalsource-directive.md) --indica una asignación entre líneas de código fuente y texto externo al código fuente  
  
 [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compilan bloques de código seleccionados  
  
 [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md) : contrae y oculta secciones de código en el editor de Visual Studio  
  
 **#Disable, #Enable** : deshabilita y habilita advertencias específicas para regiones de código.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)
