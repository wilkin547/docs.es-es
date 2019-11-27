---
title: Directivas
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: d76e10ad5ce8ad3accdc84f97146e0816048d8f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343801"
---
# <a name="directives-visual-basic"></a>Directivas de Visual Basic

Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.  
  
## <a name="in-this-section"></a>Esta sección  

 [Directiva de #Const](../../../visual-basic/language-reference/directives/const-directive.md) : definir una constante del compilador  
  
 [Directiva de #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) : indicar una asignación entre líneas de código fuente y texto externo al origen  
  
 [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compilar bloques de código seleccionados  
  
 [Directiva de #Region](../../../visual-basic/language-reference/directives/region-directive.md) : contraer y ocultar secciones de código en el editor de Visual Studio  
  
 **#Disable, #Enable** : deshabilitar y habilitar advertencias específicas para las regiones de código.  
  
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
