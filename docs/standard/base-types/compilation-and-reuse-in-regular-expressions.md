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
ms.openlocfilehash: 54f14a4f31bef00dd222686cc523935b2d9dd5fa
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279043"
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Compilar y volver a utilizar en expresiones regulares
Puede optimizar el rendimiento de aplicaciones que usan en gran medida las expresiones regulares al comprender cómo compila expresiones el motor de expresiones regulares y cómo se almacenan en caché las expresiones regulares. En este tema, se describen la compilación y el almacenamiento en caché.  
  
## <a name="compiled-regular-expressions"></a>Expresiones regulares compiladas  
 De manera predeterminada, el motor de expresiones regulares compila una expresión regular en una secuencia de instrucciones internas (son códigos de alto nivel diferentes del Lenguaje Intermedio de Microsoft, o MSIL). Cuando el motor ejecuta una expresión regular, interpreta los códigos internos.  
  
 Si un objeto <xref:System.Text.RegularExpressions.Regex> se construye con la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>, compila la expresión regular en código MSIL explícito en lugar de instrucciones internas de expresiones regulares de alto nivel. De este modo, el compilador Just-In-Time (JIT) de .NET puede convertir la expresión en código de equipo nativo para un mayor rendimiento.  El costo de construir el objeto <xref:System.Text.RegularExpressions.Regex> puede ser mayor, pero el de realizar coincidencias con él puede ser mucho más pequeño.

 Una alternativa consiste en utilizar expresiones regulares precompiladas. Puede compilar todas las expresiones en un archivo DLL reutilizable con el método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>. Esto evita la necesidad de compilar en tiempo de ejecución mientras sigue beneficiándose de la velocidad de las expresiones regulares compiladas.  
  
## <a name="the-regular-expressions-cache"></a>La caché de expresiones regulares  
 Para mejorar el rendimiento, el motor de expresiones regulares mantiene una caché de la aplicación de expresiones regulares compiladas. La caché almacena los patrones de expresiones regulares que se usan solo en las llamadas al método estático. (Los patrones de expresiones regulares proporcionados a métodos de instancia no se almacenan en caché). Esto evita la necesidad de volver a analizar una expresión en código de bytes de alto nivel cada vez que se usa.  
  
 El valor de la propiedad `static` (`Shared` en Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> determina el número máximo de expresiones regulares almacenadas en caché. De manera predeterminada, el motor de expresiones regulares almacena en caché hasta 15 expresiones regulares compiladas. Si el número de expresiones regulares compiladas supera el tamaño de la caché, se descarta la expresión regular usada menos recientemente y se almacena en caché la nueva expresión regular.  
  
 La aplicación puede reutilizar las expresiones regulares en una de las siguientes formas:  
  
- Mediante el uso de un método estático del objeto <xref:System.Text.RegularExpressions.Regex> para definir la expresión regular. Si usa un patrón de expresión regular que ya ha definido otra llamada al método estático, el motor de expresiones regulares lo recuperará de la caché. Si no está disponible en la caché, el motor compilará la expresión regular y la agregará a la caché.
  
- Al volver a usar un objeto <xref:System.Text.RegularExpressions.Regex> existente siempre que sea necesario su patrón de expresión regular.  
  
 Debido a la sobrecarga de la creación de instancias de objeto y la compilación de expresiones regulares, crear y destruir rápidamente numerosos objetos <xref:System.Text.RegularExpressions.Regex> es un proceso muy costoso. Para aplicaciones que usan un gran número de expresiones regulares diferentes, puede optimizar el rendimiento al realizar llamadas a métodos `Regex` estáticos y posiblemente al aumentar el tamaño de la caché de expresiones regulares.  
  
## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET](regular-expressions.md)
