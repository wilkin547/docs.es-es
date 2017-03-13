---
title: "C&#243;mo: Utilizar propiedades indizadas en la programaci&#243;n de interoperabilidad COM (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "propiedades indizadas [C#]"
  - "programación en Office [C#], propiedades indizadas"
  - "propiedades [C#], indizadas"
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# C&#243;mo: Utilizar propiedades indizadas en la programaci&#243;n de interoperabilidad COM (Gu&#237;a de programaci&#243;n de C#)
Las *propiedades indizadas* mejoran la manera en que se utilizan las propiedades COM con parámetros en programación de C\#.  Las propiedades indizadas funcionan junto con otras características presentadas en Visual C\# 2010, como los [argumentos con nombre y opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), un nuevo tipo \([dinámico](../../../csharp/language-reference/keywords/dynamic.md)\) y la [información de tipo incrustada](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md), para mejorar la programación en Microsoft Office.  
  
 En versiones anteriores de C\#, los métodos son solo accesibles como propiedades si el método `get` no tiene ningún parámetro y el método `set` tiene solo un parámetro de valor.  Sin embargo, no todas las propiedades COM cumplen esas restricciones.  Por ejemplo, la propiedad [Range](http://go.microsoft.com/fwlink/?LinkId=166053) tiene un descriptor de acceso `get` que requiere un parámetro para el nombre del intervalo.  Antes, como no había acceso directo a la propiedad `Range`, había que utilizar el método `get_Range`, como se muestra en el siguiente ejemplo.  
  
 [!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 Las propiedades indizadas, en cambio, permiten escribir lo siguiente:  
  
 [!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  En el ejemplo anterior, también se utiliza la característica [argumentos opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), que se incluye en Visual C\# 2010 y que permite omitir `Type.Missing`.  
  
 De forma similar, para establecer el valor de la propiedad `Value` de un objeto [Range](http://go.microsoft.com/fwlink/?LinkId=179211) de Visual C\# 2008 y versiones anteriores, se necesitan dos argumentos.  Uno proporciona un argumento para un parámetro opcional que especifica el tipo del valor del intervalo.  El otro proporciona el valor de la propiedad `Value`.  Antes de Visual C\# 2010, C\# permitía solo un argumento.  Por consiguiente, en lugar de utilizar un método set normal, había que utilizar el método `set_Value` o una propiedad diferente, [Value2](http://go.microsoft.com/fwlink/?LinkId=166050).  Estas técnicas se ilustran en los siguientes ejemplos.  En ambos ejemplos, se establece el valor de la celda A1 en `Name`.  
  
 [!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 Las propiedades indizadas, en cambio, permiten escribir el código siguiente.  
  
 [!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 El usuario no puede crear propiedades indizadas.  La característica solo admite el uso de propiedades indizadas existentes.  
  
## Ejemplo  
 El código siguiente contiene un ejemplo completo.  Para obtener más información sobre cómo preparar un proyecto con acceso a la API de Office, vea [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## Vea también  
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Cómo: Usar argumentos opcionales y con nombre en la programación de Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)   
 [Tutorial: Programación de Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)