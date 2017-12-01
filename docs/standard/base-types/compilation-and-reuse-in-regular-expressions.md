---
title: Compilar y volver a utilizar en expresiones regulares
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 76acdf2d0d2f7805ec78ea44136bfc63441b9bc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Compilar y volver a utilizar en expresiones regulares
Puede optimizar el rendimiento de aplicaciones que usan en gran medida las expresiones regulares al comprender cómo compila expresiones el motor de expresiones regulares y cómo se almacenan en caché las expresiones regulares. En este tema, se describen la compilación y el almacenamiento en caché.  
  
## <a name="compiled-regular-expressions"></a>Expresiones regulares compiladas  
 De manera predeterminada, el motor de expresiones regulares compila una expresión regular en una secuencia de instrucciones internas (son códigos de alto nivel diferentes del Lenguaje Intermedio de Microsoft, o MSIL). Cuando el motor ejecuta una expresión regular, interpreta los códigos internos.  
  
 Si un <xref:System.Text.RegularExpressions.Regex> objeto se construyó con el <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> opción, se compila la expresión regular en código MSIL explícito en lugar de instrucciones internas de expresiones regulares de alto nivel. De este modo, el compilador Just-In-Time (JIT) de .NET puede convertir la expresión en código de equipo nativo para un mayor rendimiento.  
  
En cambio, el lenguaje MSIL generado no se puede descargar. La única forma de descargar el código es descargar un dominio de aplicación completo (es decir, descargar todo el código de la aplicación). De hecho, una vez compilada una expresión regular con la <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> opción, nunca libera los recursos utilizados por la expresión compilada, incluso si la expresión regular se creó con una <xref:System.Text.RegularExpressions.Regex> objeto liberado para la recolección de elementos.  
  
 Debe tener cuidado limitar el número de expresiones regulares distintas que se compila con la <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> opción para evitar que se consuman demasiados recursos. Si una aplicación debe usar un número muy grande o ilimitado de expresiones regulares, cada expresión debe interpretarse, no compilarse. Sin embargo, si constantemente se utiliza un número pequeño de expresiones regulares, éstas deben compilarse con <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> para mejorar el rendimiento. Una alternativa consiste en utilizar expresiones regulares precompiladas. Todas las expresiones en una DLL reutilizable se compila mediante la <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> método. Esto evita la necesidad de compilar en tiempo de ejecución mientras todavía se beneficia de la velocidad de las expresiones regulares compiladas.  
  
## <a name="the-regular-expressions-cache"></a>La caché de expresiones regulares  
 Para mejorar el rendimiento, el motor de expresiones regulares mantiene una caché de la aplicación de expresiones regulares compiladas. La caché almacena los patrones de expresiones regulares que se usan solo en las llamadas al método estático. (Los patrones de expresiones regulares proporcionados a métodos de instancia no se almacenan en caché). Esto evita la necesidad de volver a analizar una expresión en código de bytes de alto nivel cada vez que se usa.  
  
 El número máximo de expresiones regulares en caché está determinado por el valor de la `static` (`Shared` en Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> propiedad. De manera predeterminada, el motor de expresiones regulares almacena en caché hasta 15 expresiones regulares compiladas. Si el número de expresiones regulares compiladas supera el tamaño de la caché, se descarta la expresión regular usada menos recientemente y se almacena en caché la nueva expresión regular.  
  
 La aplicación puede aprovechar las expresiones regulares compiladas previamente en una de las siguientes formas:  
  
-   Mediante el uso de un método estático de la <xref:System.Text.RegularExpressions.Regex> objeto para definir la expresión regular. Si usa un patrón de expresión regular que ya se ha definido en otra llamada al método estático, el motor de expresiones regulares lo recuperará de la caché. De lo contrario, el motor compilará la expresión regular y la agregará a la caché.  
  
-   Si se reutiliza una existente <xref:System.Text.RegularExpressions.Regex> objeto siempre y cuando se necesita su patrón de expresión regular.  
  
 Debido a la sobrecarga de la creación de instancias de objeto y compilación de la expresión regular, crear y destruir rápidamente numerosos <xref:System.Text.RegularExpressions.Regex> objetos es un proceso muy costoso. Para las aplicaciones que utilizan un gran número de expresiones regulares diferentes, puede optimizar el rendimiento mediante llamadas a estática `Regex` métodos y posiblemente por aumentar el tamaño de la memoria caché de expresión regular.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones regulares de .NET](../../../docs/standard/base-types/regular-expressions.md)
