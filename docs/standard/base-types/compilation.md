---
title: Compilar y volver a usar en expresiones regulares
description: Compilar y volver a usar en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3adea434-e2ed-4023-b4f5-b0608b4cf53f
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 1832403174276e48dc1857be8ff11fba2b9a250c

---

# <a name="compilation-and-reuse-in-regular-expressions"></a>Compilar y volver a usar en expresiones regulares

Puede optimizar el rendimiento de aplicaciones que usan en gran medida las expresiones regulares al comprender cómo compila expresiones el motor de expresiones regulares y cómo se almacenan en caché las expresiones regulares. En este tema, se describen la compilación y el almacenamiento en caché.

## <a name="compiled-regular-expressions"></a>Expresiones regulares compiladas

De manera predeterminada, el motor de expresiones regulares compila una expresión regular en una secuencia de instrucciones internas (son códigos de alto nivel diferentes del Lenguaje Intermedio de Microsoft, o MSIL). Cuando el motor ejecuta una expresión regular, interpreta los códigos internos.

Si un objeto [Regex](xref:System.Text.RegularExpressions.Regex) se construye con la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled), compila la expresión regular en código MSIL explícito en lugar de instrucciones internas de expresiones regulares de alto nivel. De este modo, el compilador Just-In-Time (JIT) de .NET puede convertir la expresión en código de equipo nativo para un mayor rendimiento.

En cambio, el lenguaje MSIL generado no se puede descargar. La única forma de descargar el código es descargar un dominio de aplicación completo (es decir, descargar todo el código de la aplicación). De hecho, una vez compilada una expresión regular con la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled), .NET nunca lanza los recursos usados por la expresión compilada, aunque la expresión regular la haya creado un objeto [Regex](xref:System.Text.RegularExpressions.Regex) liberado para la recolección de elementos no utilizados.

Debe asegurarse de limitar el número de expresiones regulares distintas que compila con la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) para evitar que se consuman demasiados recursos. Si una aplicación debe usar un número muy grande o ilimitado de expresiones regulares, cada expresión debe interpretarse, no compilarse. En cambio, si se usa varias veces un número pequeño de expresiones regulares, estas deben compilarse con [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) para mejorar el rendimiento. 

## <a name="the-regular-expressions-cache"></a>La caché de expresiones regulares

Para mejorar el rendimiento, el motor de expresiones regulares mantiene una caché de la aplicación de expresiones regulares compiladas. La caché almacena los patrones de expresiones regulares que se usan solo en las llamadas al método estático. (Los patrones de expresiones regulares proporcionados a métodos de instancia no se almacenan en caché). Esto evita la necesidad de volver a analizar una expresión en código de bytes de alto nivel cada vez que se usa.

El valor de la propiedad `static` (`Shared` en Visual Basic) [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) determina el número máximo de expresiones regulares almacenadas en caché. De manera predeterminada, el motor de expresiones regulares almacena en caché hasta 15 expresiones regulares compiladas. Si el número de expresiones regulares compiladas supera el tamaño de la caché, se descarta la expresión regular usada menos recientemente y se almacena en caché la nueva expresión regular. 

La aplicación puede aprovechar las expresiones regulares compiladas previamente en una de las siguientes formas:

* Mediante el uso de un método estático del objeto [Regex](xref:System.Text.RegularExpressions.Regex) para definir la expresión regular. Si usa un patrón de expresión regular que ya se ha definido en otra llamada al método estático, el motor de expresiones regulares lo recuperará de la caché. De lo contrario, el motor compilará la expresión regular y la agregará a la caché.

* Al volver a usar un objeto [Regex](xref:System.Text.RegularExpressions.Regex) existente siempre que sea necesario su patrón de expresión regular.


Debido a la sobrecarga de la creación de instancias de objeto y la compilación de expresiones regulares, crear y destruir rápidamente numerosos objetos [Regex](xref:System.Text.RegularExpressions.Regex) es un proceso muy costoso. Para aplicaciones que usan un gran número de expresiones regulares diferentes, puede optimizar el rendimiento al realizar llamadas a métodos [Regex](xref:System.Text.RegularExpressions.Regex) estáticos y posiblemente al aumentar el tamaño de la caché de expresiones regulares.

## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)




<!--HONumber=Nov16_HO1-->


