---
title: Uso de tipo dinámico (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic [C#], about dynamic type
- dynamic type [C#]
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
ms.openlocfilehash: 67eb39fd6f2077d2adf1d38d001e801b815d687d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336643"
---
# <a name="using-type-dynamic-c-programming-guide"></a>Uso de tipo dinámico (Guía de programación de C#)
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] introduce un nuevo tipo, `dynamic`. Se trata de un tipo estático, pero un objeto de tipo `dynamic` omite la comprobación de tipos estáticos. En la mayoría de los casos, funciona como si tuviera el tipo `object`. En tiempo de compilación, se supone que un elemento con tipo `dynamic` admite cualquier operación. Por consiguiente, no tendrá que preocuparse de si el objeto obtiene su valor de una API de COM, de un lenguaje dinámico como IronPython, del Document Object Model (DOM) HTML, de la reflexión o de otro lugar en el programa. Pero si el código no es válido, los errores se detectan en tiempo de ejecución.  
  
 Por ejemplo, si la instancia de método `exampleMethod1` del código siguiente solo tiene un parámetro, el compilador reconoce que la primera llamada al método, `ec.exampleMethod1(10, 4)`, no es válida porque contiene dos argumentos. La llamada genera un error del compilador. El compilador no comprueba la segunda llamada al método, `dynamic_ec.exampleMethod1(10, 4)`, porque el tipo de `dynamic_ec` es `dynamic`. Por consiguiente, no se notifica ningún error del compilador. Pero el error no pasa inadvertido indefinidamente. Se detecta en tiempo de ejecución y genera una excepción en tiempo de ejecución.  
  
 [!code-csharp[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]  
  
 [!code-csharp[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]  
  
 El rol del compilador en estos ejemplos consiste en empaquetar información sobre lo que cada instrucción se propone para el objeto o la expresión con el tipo `dynamic`. En tiempo de ejecución, la información almacenada se examina y cualquier instrucción que no sea válida genera una excepción en tiempo de ejecución.  
  
 El resultado de la mayoría de las operaciones dinámicas es `dynamic`. Por ejemplo, si se sitúa el puntero del mouse sobre el uso de `testSum` en el ejemplo siguiente, IntelliSense muestra el tipo **(local variable) dynamic testSum**.  
  
 [!code-csharp[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]  
  
 Las operaciones en las que el resultado no es `dynamic` incluyen las conversiones de `dynamic` a otro tipo, así como llamadas de constructor que incluyen argumentos de tipo `dynamic`. Por ejemplo, el tipo de `testInstance` en la siguiente declaración es `ExampleClass`, no `dynamic`.  
  
 [!code-csharp[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]  
  
 En la siguiente sección, "Conversiones", se muestran ejemplos de conversión.  
  
## <a name="conversions"></a>Conversiones  
 Las conversiones entre objetos dinámicos y de otro tipo son fáciles. Esto permite al desarrollador cambiar entre el comportamiento dinámico y no dinámico.  
  
 Cualquier objeto se puede convertir implícitamente al tipo dinámico, tal y como se muestra en los ejemplos siguientes.  
  
 [!code-csharp[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]  
  
 En cambio, una conversión implícita se puede aplicar dinámicamente a cualquier expresión de tipo `dynamic`.  
  
 [!code-csharp[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]  
  
## <a name="overload-resolution-with-arguments-of-type-dynamic"></a>Resolución de sobrecarga con argumentos de tipo dinámico  
 La resolución de sobrecarga se produce en tiempo de ejecución y no en tiempo de compilación si uno o varios argumentos de una llamada de método tienen el tipo `dynamic` o si el receptor de la llamada de método es de tipo `dynamic`. En el ejemplo siguiente, si el único método `exampleMethod2` accesible se define para que tome un argumento de cadena, al enviar `d1` como argumento no se produce un error del compilador, pero sí se genera una excepción en tiempo de ejecución. La resolución de sobrecarga no se produce en tiempo de ejecución porque el tipo en tiempo de ejecución de `d1` es `int`, y `exampleMethod2` requiere una cadena.  
  
 [!code-csharp[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]  
  
## <a name="dynamic-language-runtime"></a>Dynamic Language Runtime  
 Dynamic Language Runtime (DLR) es una nueva API en [!INCLUDE[net_v40_short](~/includes/net-v40-short-md.md)]. Proporciona la infraestructura que admite el tipo `dynamic` en C# y también la implementación de lenguajes de programación dinámicos como IronPython e IronRuby. Para obtener más información sobre el entorno DLR, vea [Dynamic Language Runtime Overview](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md) (Información general sobre Dynamic Language Runtime).  
  
## <a name="com-interop"></a>Interoperabilidad COM  
 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] incluye varias características que mejoran la experiencia de interoperar con API de COM tales como las API de automatización de Office. Entre las mejoras se incluye el uso del tipo `dynamic` y de [argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Muchos métodos COM permiten variaciones en los tipos de argumento y el tipo de valor devuelto mediante la designación de los tipos como `object`. Esto requería una conversión explícita de los valores para coordinarlos con variables fuertemente tipadas en C#. Si se compila con la opción [/link (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/link-compiler-option.md), la introducción del tipo `dynamic` le permite tratar las repeticiones de `object` en las firmas COM como si fueran de tipo `dynamic` y así evitar gran parte de la conversión. Por ejemplo, las instrucciones siguientes comparan cómo se accede a una celda de una hoja de cálculo de Microsoft Office Excel con el tipo `dynamic` y sin el tipo `dynamic`.  
  
 [!code-csharp[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]  
  
 [!code-csharp[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Description|  
|-----------|-----------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Describe el uso de la palabra clave `dynamic`.|  
|[Información general sobre Dynamic Language Runtime](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)|Ofrece información general sobre DLR, que es un entorno en tiempo de ejecución que agrega un conjunto de servicios para lenguajes dinámicos en Common Language Runtime (CLR).|  
|[Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])|Ofrece instrucciones paso a paso para crear un objeto dinámico personalizado y para crear un proyecto que acceda a una biblioteca de `IronPython`.|  
|[Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Muestra cómo crear un proyecto que use argumentos opcionales y con nombre, el tipo `dynamic` y otras mejoras que simplifican el acceso a objetos de la API de Office.|
