---
title: "Uso de tipo din&#225;mico (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "dinámico [C#], acerca del tipo dinámico"
  - "tipo dinámico [C#]"
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Uso de tipo din&#225;mico (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] presenta un nuevo tipo, `dynamic`.  Se trata de un tipo estático, pero un objeto de tipo `dynamic` omite la comprobación de tipos en tiempo de compilación.  En la mayoría de los casos, funciona como si tuviera el tipo `object`.  En tiempo de compilación, se supone que un elemento de tipo `dynamic` admite cualquier operación.  Por lo tanto, no tiene que preocuparse de si el objeto obtiene su valor de una API de COM, de un lenguaje dinámico como IronPython, de DOM \(Document Object Model\) HTML, de la reflexión o de cualquier otra parte del programa.  Sin embargo, si el código no es válido, los errores se detectan en tiempo de ejecución.  
  
 Por ejemplo, si el método de instancia `exampleMethod1` del código siguiente solo tiene un parámetro, el compilador reconoce que la primera llamada al método \(`ec.exampleMethod1(10, 4)`\) no es válida, ya que contiene dos argumentos.  La llamada provoca un error del compilador.  El compilador no comprueba la segunda llamada al método, `dynamic_ec.exampleMethod1(10, 4)`, porque el tipo de `dynamic_ec` es `dynamic`.  Por lo tanto, no se notifica ningún error del compilador.  Sin embargo, el error no pasa desapercibido indefinidamente.  Se detecta en tiempo de ejecución y produce una excepción en tiempo de ejecución.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_2.cs)]  
  
 El rol del compilador en estos ejemplos consiste en empaquetar información sobre la acción que cada una de las instrucciones propone para el objeto o la expresión de tipo `dynamic`.  En tiempo de ejecución, la información almacenada se examina y cualquier instrucción no válida produce una excepción en tiempo de ejecución.  
  
 El resultado de la mayoría de las operaciones dinámicas es `dynamic` en sí.  Por ejemplo, si coloca el puntero del mouse sobre el uso de `testSum` en el siguiente ejemplo, IntelliSense muestra el tipo **\(variable local\) dynamic testSum**.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_3.cs)]  
  
 Las operaciones en las que el resultado no es `dynamic` incluyen las conversiones de `dynamic` en otro tipo, así como llamadas a constructor que incluyen argumentos de tipo `dynamic`.  Por ejemplo, el tipo de `testInstance` en la siguiente declaración es `ExampleClass`, no `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_4.cs)]  
  
 En la siguiente sección, "Conversiones", se muestran ejemplos de conversión.  
  
## Conversiones  
 Las conversiones entre los objetos dinámicos y de otros tipos son fáciles.  Esto permite al desarrollador cambiar entre un comportamiento dinámico y no dinámico.  
  
 Cualquier objeto se puede convertir en el tipo dinámico implícitamente, como se muestra en los siguientes ejemplos.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_5.cs)]  
  
 Por el contrario, una conversión implícita se puede aplicar dinámicamente a cualquier expresión de tipo `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_6.cs)]  
  
## Resolución de sobrecarga con argumentos de tipo dinámico  
 La resolución de sobrecarga se produce en tiempo de ejecución en lugar de en tiempo de compilación si uno o más de los argumentos de una llamada de método tiene el tipo `dynamic` o si el receptor de dicha llamada es de tipo `dynamic`.  En el ejemplo siguiente, si el único método `exampleMethod2` accesible se define de forma que tome un argumento de cadena, el envío de `d1` como argumento no produce un error del compilador, pero sí una excepción en tiempo de ejecución.  La resolución de sobrecarga origina un error en tiempo de ejecución porque el tipo de `d1` en tiempo de ejecución es `int` y `exampleMethod2` requiere una cadena.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_7.cs)]  
  
## Dynamic Language Runtime  
 Dynamic Language Runtime \(DLR\) es una nueva API en [!INCLUDE[net_v40_short](../../../csharp/programming-guide/types/includes/net-v40-short-md.md)].  Proporciona la infraestructura que admite el tipo `dynamic` en C\# y también la implementación de lenguajes de programación dinámicos como IronPython e IronRuby.  Para obtener más información acerca de DLR, vea [Dynamic Language Runtime Overview](../Topic/Dynamic%20Language%20Runtime%20Overview.md).  
  
## Interoperabilidad COM  
 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)]incluye varias características que mejoran la experiencia de interoperar con las API de COM, como las API de automatización de Office.  Entre las mejoras se encuentra el uso del tipo `dynamic`, así como de los [argumentos con nombre y opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Muchos métodos COM permiten la variación en los tipos de argumento y el tipo de valor devuelto mediante la designación de los tipos como `object`.  Esto ha hecho necesario la conversión explícita de los valores para coordinarlos con las variables fuertemente tipadas en C\#.  Si compila con la opción [\/link \(Link to COM Assembly\)](../../../csharp/language-reference/compiler-options/link-compiler-option.md), la introducción del tipo `dynamic` permite tratar las apariciones de `object` en los prototipos COM como si fueran de tipo `dynamic` y evitar así gran parte de la conversión.  Por ejemplo, en las instrucciones siguientes se contrasta la forma en que se tiene acceso a una celda en una hoja de cálculo de Microsoft Office Excel con el tipo `dynamic` y sin el tipo `dynamic`.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#12)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#13)]  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Describe el uso de la palabra clave `dynamic`.|  
|[Dynamic Language Runtime Overview](../Topic/Dynamic%20Language%20Runtime%20Overview.md)|Proporciona información general sobre DLR, un entorno en tiempo de ejecución que agrega un conjunto de servicios para lenguajes dinámicos a Common Language Runtime \(CLR\).|  
|[Tutorial: Crear y utilizar objetos dinámicos](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|Proporciona instrucciones paso a paso para crear un objeto dinámico personalizado y crear un proyecto que obtiene acceso a una biblioteca de `IronPython`.|  
|[Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Muestra cómo crear un proyecto que usa argumentos con nombres y opcionales, el tipo `dynamic` y otras mejoras que simplifican el acceso a los objetos de la API de Office.|