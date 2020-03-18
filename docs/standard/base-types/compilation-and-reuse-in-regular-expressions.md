---
title: Compilar y volver a utilizar en expresiones regulares
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 3e1dfe8373145286b03e503f038e267ff0d4c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091730"
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Compilar y volver a utilizar en expresiones regulares
Puede optimizar el rendimiento de aplicaciones que usan en gran medida las expresiones regulares al comprender cómo compila expresiones el motor de expresiones regulares y cómo se almacenan en caché las expresiones regulares. En este tema, se describen la compilación y el almacenamiento en caché.  
  
## <a name="compiled-regular-expressions"></a>Expresiones regulares compiladas  
 De manera predeterminada, el motor de expresiones regulares compila una expresión regular en una secuencia de instrucciones internas (son códigos de alto nivel diferentes del Lenguaje Intermedio de Microsoft, o MSIL). Cuando el motor ejecuta una expresión regular, interpreta los códigos internos.  
  
 Si un objeto <xref:System.Text.RegularExpressions.Regex> se construye con la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>, compila la expresión regular en código MSIL explícito en lugar de instrucciones internas de expresiones regulares de alto nivel. De este modo, el compilador Just-In-Time (JIT) de .NET puede convertir la expresión en código de equipo nativo para un mayor rendimiento.  
  
En cambio, el lenguaje MSIL generado no se puede descargar. La única forma de descargar el código es descargar un dominio de aplicación completo (es decir, descargar todo el código de la aplicación). De hecho, una vez compilada una expresión regular con la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>, .NET nunca lanza los recursos usados por la expresión compilada, aunque la expresión regular la haya creado un objeto <xref:System.Text.RegularExpressions.Regex> liberado para la recolección de elementos no utilizados.  
  
 Debe asegurarse de limitar el número de expresiones regulares distintas que compila con la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> para evitar que se consuman demasiados recursos. Si una aplicación debe usar un número muy grande o ilimitado de expresiones regulares, cada expresión debe interpretarse, no compilarse. En cambio, si se usa varias veces un número pequeño de expresiones regulares, estas deben compilarse con <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> para mejorar el rendimiento. Una alternativa consiste en utilizar expresiones regulares precompiladas. Puede compilar todas las expresiones en un archivo DLL reutilizable con el método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>. Esto evita la necesidad de compilar en tiempo de ejecución mientras todavía se beneficia de la velocidad de las expresiones regulares compiladas.  
  
## <a name="the-regular-expressions-cache"></a>La caché de expresiones regulares  
 Para mejorar el rendimiento, el motor de expresiones regulares mantiene una caché de la aplicación de expresiones regulares compiladas. La caché almacena los patrones de expresiones regulares que se usan solo en las llamadas al método estático. (Los patrones de expresiones regulares proporcionados a métodos de instancia no se almacenan en caché). Esto evita la necesidad de volver a analizar una expresión en código de bytes de alto nivel cada vez que se usa.  
  
 El valor de la propiedad `static` (`Shared` en Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> determina el número máximo de expresiones regulares almacenadas en caché. De manera predeterminada, el motor de expresiones regulares almacena en caché hasta 15 expresiones regulares compiladas. Si el número de expresiones regulares compiladas supera el tamaño de la caché, se descarta la expresión regular usada menos recientemente y se almacena en caché la nueva expresión regular.  
  
 La aplicación puede aprovechar las expresiones regulares compiladas previamente en una de las siguientes formas:  
  
- Mediante el uso de un método estático del objeto <xref:System.Text.RegularExpressions.Regex> para definir la expresión regular. Si usa un patrón de expresión regular que ya se ha definido en otra llamada al método estático, el motor de expresiones regulares lo recuperará de la caché. De lo contrario, el motor compilará la expresión regular y la agregará a la caché.  
  
- Al volver a usar un objeto <xref:System.Text.RegularExpressions.Regex> existente siempre que sea necesario su patrón de expresión regular.  
  
 Debido a la sobrecarga de la creación de instancias de objeto y la compilación de expresiones regulares, crear y destruir rápidamente numerosos objetos <xref:System.Text.RegularExpressions.Regex> es un proceso muy costoso. Para aplicaciones que usan un gran número de expresiones regulares diferentes, puede optimizar el rendimiento al realizar llamadas a métodos `Regex` estáticos y posiblemente al aumentar el tamaño de la caché de expresiones regulares.  
  
## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET](../../../docs/standard/base-types/regular-expressions.md)
