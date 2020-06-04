---
title: Directivas
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410002"
---
# <a name="directives-visual-basic"></a>Directivas de Visual Basic

Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.  
  
## <a name="in-this-section"></a>En esta sección  

 [Directiva de #Const](const-directive.md) : definir una constante del compilador  
  
 [Directiva de #ExternalSource](externalsource-directive.md) : indicar una asignación entre líneas de código fuente y texto externo al origen  
  
 [#If... Then... #Else directivas](if-then-else-directives.md) : compilar bloques de código seleccionados  
  
 [Directiva de #Region](region-directive.md) : contraer y ocultar secciones de código en el editor de Visual Studio  
  
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

 [Referencia del lenguaje Visual Basic](../index.md)  
  