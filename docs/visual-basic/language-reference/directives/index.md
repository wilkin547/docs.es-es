---
title: Directivas de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032062"
---
# <a name="directives-visual-basic"></a>Directivas de Visual Basic
Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.  
  
## <a name="in-this-section"></a>En esta sección  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md) : definir una constante del compilador  
  
 [#ExternalSource (directiva)](../../../visual-basic/language-reference/directives/externalsource-directive.md) --indicar una asignación entre líneas de código fuente y texto externo al código fuente  
  
 [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --compilar bloques de código seleccionados  
  
 [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md) : contraer y ocultar secciones de código en el editor de Visual Studio  
  
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
