---
title: Directivas
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838148"
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
  