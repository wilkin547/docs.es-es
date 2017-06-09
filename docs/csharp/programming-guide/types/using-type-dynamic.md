---
title: "Uso de tipo dinámico (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#], about dynamic type
- dynamic type [C#]
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 7e2310df174a7c38fafba3fed4e4bd3de4fa377a
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="using-type-dynamic-c-programming-guide"></a>Uso de tipo dinámico (Guía de programación de C#)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] introduce un nuevo tipo, `dynamic`. Se trata de un tipo estático, pero un objeto de tipo `dynamic` omite la comprobación de tipos estáticos. En la mayoría de los casos, funciona como si tuviera el tipo `object`. En tiempo de compilación, se supone que un elemento con tipo `dynamic` admite cualquier operación. Por consiguiente, no tendrá que preocuparse de si el objeto obtiene su valor de una API de COM, de un lenguaje dinámico como IronPython, del Document Object Model (DOM) HTML, de la reflexión o de otro lugar en el programa. Pero si el código no es válido, los errores se detectan en tiempo de ejecución.  
  
 Por ejemplo, si la instancia de método `exampleMethod1` del código siguiente solo tiene un parámetro, el compilador reconoce que la primera llamada al método, `ec.exampleMethod1(10, 4)`, no es válida porque contiene dos argumentos. La llamada genera un error del compilador. El compilador no comprueba la segunda llamada al método, `dynamic_ec.exampleMethod1(10, 4)`, porque el tipo de `dynamic_ec` es `dynamic`. Por consiguiente, no se notifica ningún error del compilador. Pero el error no pasa inadvertido indefinidamente. Se detecta en tiempo de ejecución y genera una excepción en tiempo de ejecución.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]  
  
 El rol del compilador en estos ejemplos consiste en empaquetar información sobre lo que cada instrucción se propone para el objeto o la expresión con el tipo `dynamic`. En tiempo de ejecución, la información almacenada se examina y cualquier instrucción que no sea válida genera una excepción en tiempo de ejecución.  
  
 El resultado de la mayoría de las operaciones dinámicas es `dynamic`. Por ejemplo, si se sitúa el puntero del mouse sobre el uso de `testSum` en el ejemplo siguiente, IntelliSense muestra el tipo **(local variable) dynamic testSum**.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]  
  
 Las operaciones en las que el resultado no es `dynamic` incluyen las conversiones de `dynamic` a otro tipo, así como llamadas de constructor que incluyen argumentos de tipo `dynamic`. Por ejemplo, el tipo de `testInstance` en la siguiente declaración es `ExampleClass`, no `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]  
  
 En la siguiente sección, "Conversiones", se muestran ejemplos de conversión.  
  
## <a name="conversions"></a>Conversiones  
 Las conversiones entre objetos dinámicos y de otro tipo son fáciles. Esto permite al desarrollador cambiar entre el comportamiento dinámico y no dinámico.  
  
 Cualquier objeto se puede convertir implícitamente al tipo dinámico, tal y como se muestra en los ejemplos siguientes.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]  
  
 En cambio, una conversión implícita se puede aplicar dinámicamente a cualquier expresión de tipo `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]  
  
## <a name="overload-resolution-with-arguments-of-type-dynamic"></a>Resolución de sobrecarga con argumentos de tipo dinámico  
 La resolución de sobrecarga se produce en tiempo de ejecución y no en tiempo de compilación si uno o varios argumentos de una llamada de método tienen el tipo `dynamic` o si el receptor de la llamada de método es de tipo `dynamic`. En el ejemplo siguiente, si el único método `exampleMethod2` accesible se define para que tome un argumento de cadena, al enviar `d1` como argumento no se produce un error del compilador, pero sí se genera una excepción en tiempo de ejecución. La resolución de sobrecarga no se produce en tiempo de ejecución porque el tipo en tiempo de ejecución de `d1` es `int`, y `exampleMethod2` requiere una cadena.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]  
  
## <a name="dynamic-language-runtime"></a>Dynamic Language Runtime  
 Dynamic Language Runtime (DLR) es una nueva API en [!INCLUDE[net_v40_short](~/includes/net-v40-short-md.md)]. Proporciona la infraestructura que admite el tipo `dynamic` en C# y también la implementación de lenguajes de programación dinámicos como IronPython e IronRuby. Para obtener más información sobre el entorno DLR, vea [Dynamic Language Runtime Overview](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md) (Información general sobre Dynamic Language Runtime).  
  
## <a name="com-interop"></a>Interoperabilidad COM  
 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] incluye varias características que mejoran la experiencia de interoperar con API de COM tales como las API de automatización de Office. Entre las mejoras se incluye el uso del tipo `dynamic` y de [argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Muchos métodos COM permiten variaciones en los tipos de argumento y el tipo de valor devuelto mediante la designación de los tipos como `object`. Esto requería una conversión explícita de los valores para coordinarlos con variables fuertemente tipadas en C#. Si se compila con la opción [/link (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/link-compiler-option.md), la introducción del tipo `dynamic` le permite tratar las repeticiones de `object` en las firmas COM como si fueran de tipo `dynamic` y así evitar gran parte de la conversión. Por ejemplo, las instrucciones siguientes comparan cómo se accede a una celda de una hoja de cálculo de Microsoft Office Excel con el tipo `dynamic` y sin el tipo `dynamic`.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Describe el uso de la palabra clave `dynamic`.|  
|[Información general sobre Dynamic Language Runtime](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)|Ofrece información general sobre DLR, que es un entorno en tiempo de ejecución que agrega un conjunto de servicios para lenguajes dinámicos en Common Language Runtime (CLR).|  
|[Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])|Ofrece instrucciones paso a paso para crear un objeto dinámico personalizado y para crear un proyecto que acceda a una biblioteca de `IronPython`.|  
|[Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Muestra cómo crear un proyecto que use argumentos opcionales y con nombre, el tipo `dynamic` y otras mejoras que simplifican el acceso a objetos de la API de Office.|
