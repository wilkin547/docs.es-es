---
title: "Compilar y volver a utilizar en expresiones regulares | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "expresiones regulares de .NET Framework, compilación"
  - "expresiones regulares de .NET Framework, motores"
  - "compilación, expresiones regulares"
  - "analizar texto con expresiones regulares, compilación"
  - "coincidencia de patrones con expresiones regulares, compilación"
  - "expresiones regulares, compilación"
  - "expresiones regulares, motores"
  - "buscar con expresiones regulares, compilación"
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Compilar y volver a utilizar en expresiones regulares
Para optimizar el rendimiento de las aplicaciones que utilizan con frecuencia expresiones regulares, debe comprender cómo compila las expresiones el motor de expresiones regulares y cómo se almacenan las expresiones regulares en la memoria caché.  En este tema se describe tanto la compilación como el almacenamiento en caché.  
  
## Expresiones regulares compiladas  
 De forma predeterminada, el motor de búsqueda de expresiones regulares compila una expresión regular en una secuencia de instrucciones internas \(códigos de alto nivel distintos del lenguaje intermedio de Microsoft o MSIL\).  Cuando el motor de búsqueda ejecuta una expresión regular, interpreta los códigos internos.  
  
 Si se crea un objeto <xref:System.Text.RegularExpressions.Regex> con la opción <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, compila la expresión regular en código MSIL explícito en lugar de hacerlo en instrucciones internas de expresiones regulares de alto nivel.  Esto le permite al compilador Just\-in\-time \(JIT\) de .NET Framework convertir la expresión en código máquina nativo para proporcionar un mayor rendimiento.  
  
 Sin embargo, el código MSIL generado no se puede descargar.  El único modo de descargar código es descargar todo el dominio de la aplicación \(es decir, descargar todo el código de la aplicación\).  De hecho, una vez compilada una expresión regular con la opción <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, .NET Framework nunca libera los recursos utilizados por la expresión compilada, aunque esta haya sido creada por un objeto <xref:System.Text.RegularExpressions.Regex> que ya fue liberado para la recolección de elementos no utilizados.  
  
 Debe procurar limitar el número de expresiones regulares distintas que vaya a compilar con la opción <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> para evitar que se consuman demasiados recursos.  Si una aplicación necesita utilizar un número muy grande o ilimitado de expresiones regulares, cada una de ellas deberá interpretarse, y no compilarse.  No obstante, si se utiliza de forma repetida un número pequeño de expresiones regulares, estas se deben compilar con <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> para mejorar el rendimiento.  Otra alternativa consiste en utilizar expresiones regulares precompiladas.  Puede compilar todas las expresiones en una DLL reutilizable utilizando el método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>.  Así se evita la necesidad de compilar en tiempo de ejecución mientras que aún se beneficia de la velocidad de las expresiones regulares compiladas.  
  
## Caché de expresiones regulares  
 Para mejorar el rendimiento, el motor de expresiones regulares mantiene una caché en el nivel de aplicación para las expresiones regulares compiladas.  La caché almacena los patrones de expresiones regulares utilizados solo en llamadas a métodos estáticos. \(En la memoria caché no se almacenan los patrones de expresiones regulares suministrados a métodos de instancias\). De esta forma se evita tener que volver a analizar una expresión en código de bytes de alto nivel cada vez que se utiliza.  
  
 El valor de la propiedad `static` \(`Shared` en Visual Basic\) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=fullName> determina el número máximo de expresiones regulares almacenadas en caché.  De forma predeterminada, el motor de expresiones regulares almacena en memoria caché hasta 15 expresiones regulares compiladas.  Si el número de expresiones regulares compiladas supera el tamaño de la memoria caché, se descarta la expresión regular utilizada menos recientemente y se almacena en caché la nueva expresión regular.  
  
> [!IMPORTANT]
>  La manera en que las expresiones regulares se almacenan en la memoria caché en .NET Framework 2.0 difiere mucho de las versiones 1.0 y 1.1 de .NET Framework.  En .NET Framework 1.0 y 1.1, se almacenaban en memoria caché todas las expresiones regulares, tanto las usadas en llamadas a métodos estáticos como las usadas en llamadas a métodos de instancias.  La caché se ampliaba automáticamente para almacenar las nuevas expresiones regulares.  En .NET Framework 2.0, solo se almacenan en caché las expresiones regulares utilizadas en llamadas a métodos estáticos.  De forma predeterminada, se almacenan en caché las últimas 15 expresiones regulares, aunque se puede ajustar el tamaño de la caché estableciendo el valor de la propiedad <xref:System.Text.RegularExpressions.Regex.CacheSize%2A>.  
  
 La aplicación puede aprovechar las ventajas de las expresiones regulares precompiladas de una de las dos maneras siguientes:  
  
-   Utilizando un método estático del objeto <xref:System.Text.RegularExpressions.Regex> para definir la expresión regular.  Si va a utilizar un patrón de expresión regular ya definido en otra llamada a un método estático, el motor de expresiones regulares lo recuperará de la caché.  En caso contrario, el motor compilará la expresión regular y la agregará a la caché.  
  
-   Reutilizando un objeto <xref:System.Text.RegularExpressions.Regex> existente siempre que se necesite su patrón de expresión regular.  
  
 Debido a la sobrecarga que provoca la creación de instancias de objetos y la compilación de expresiones regulares, crear y destruir rápidamente numerosos objetos <xref:System.Text.RegularExpressions.Regex> es un proceso muy costoso.  Para aplicaciones que utilizan un gran número de expresiones regulares diferentes, puede optimizar el rendimiento utilizando llamadas a métodos `Regex` estáticos y, posiblemente, aumentando el tamaño de la caché de expresiones regulares.  
  
## Vea también  
 [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)