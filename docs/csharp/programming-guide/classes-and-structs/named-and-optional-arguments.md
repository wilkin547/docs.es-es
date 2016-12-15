---
title: "Argumentos opcionales y con nombre (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "namedParameter_CSharpKeyword"
  - "cs_namedParameter"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "argumentos [C#], con nombre"
  - "argumentos [C#], opcionales"
  - "argumentos opcionales y con nombre [C#]"
  - "argumentos con nombre [C#]"
  - "argumentos opcionales [C#]"
  - "parámetros [C#], con nombre"
  - "parámetros [C#], opcionales"
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
caps.handback.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Argumentos opcionales y con nombre (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] presenta los argumentos opcionales y con nombre.  Los *argumentos con nombre* permiten especificar un argumento para un parámetro determinado mediante la asociación del argumento al nombre del parámetro, no a la posición de este en la lista de parámetros.  Los *argumentos opcionales* permiten omitir argumentos para algunos parámetros.  Ambas técnicas se pueden usar con los métodos, indizadores, constructores y delegados.  
  
 Al usar argumentos opcionales y con nombre, los argumentos se evalúan en el orden en que aparecen en la lista de argumentos, no en la lista de parámetros.  
  
 El uso conjunto de los parámetros opcionales y con nombre permite proporcionar argumentos solamente para unos cuantos parámetros de una lista de parámetros opcionales.  Esta capacidad facilita enormemente las llamadas a las interfaces COM, como las API de automatización de Microsoft Office.  
  
## Argumentos con nombre  
 Los argumentos con nombre le liberan de la necesidad de recordar o buscar el orden de los parámetros en las listas correspondientes de los métodos a los que se ha llamado.  El parámetro de cada argumento se puede especificar mediante el nombre del parámetro.  Por ejemplo, se puede llamar a una función que calcula el índice de masa corporal \(IMC\) de la manera estándar, mediante el envío de argumentos para el peso y el alto por posición, en el orden definido por la función.  
  
 `CalculateBMI(123, 64);`  
  
 Si no recuerda el orden de los parámetros pero conoce sus nombres, puede enviar los argumentos en cualquier orden: el peso o el alto en primer lugar indistintamente.  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 Los argumentos con nombre también mejoran la legibilidad del código al identificar qué representa cada argumento.  
  
 Un argumento con nombre puede aparecer después de los argumentos posicionales, como se muestra aquí.  
  
 `CalculateBMI(123, height: 64);`  
  
 Sin embargo, un argumento posicional no puede ir después de un argumento con nombre.  La siguiente instrucción produce un error del compilador.  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## Ejemplo  
 El código siguiente implementa los ejemplos de esta sección.  
  
 [!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## Argumentos opcionales  
 En la definición de un método, constructor, indizador o delegado se puede especificar si sus parámetros son obligatorios u opcionales.  Todas las llamadas deben proporcionar argumentos para todos los parámetros obligatorios, pero pueden omitir los argumentos para los parámetros opcionales.  
  
 Cada parámetro opcional tiene un valor predeterminado como parte de su definición.  Si no se envía ningún argumento para ese parámetro, se utiliza el valor predeterminado.  un valor predeterminado debe ser uno de los siguientes tipos de expresiones:  
  
-   una expresión constante;  
  
-   una expresión de formulario `new ValType()`, donde es un tipo de valor `ValType` , como [enumeración](../../../csharp/language-reference/keywords/enum.md) o [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);  
  
-   una expresión de formulario [valor predeterminado \(ValType\)](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md), donde es un tipo de valor `ValType` .  
  
 Los parámetros opcionales se definen al final de la lista de parámetros, después de los parámetros obligatorios.  Si el llamador proporciona un argumento para cualquiera de los parámetros opcionales de una sucesión de este tipo, debe proporcionar argumentos para todos los parámetros opcionales anteriores.  No se admiten los espacios separados por comas en la lista de argumentos.  Por ejemplo, en el siguiente código, se define el método de instancia `ExampleMethod` con un parámetro obligatorio y dos parámetros opcionales.  
  
 [!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 La siguiente llamada a `ExampleMethod` genera un error del compilador, porque se ha proporcionado un argumento para el tercer parámetro pero no para el segundo.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Sin embargo, si conoce el nombre del tercer parámetro, puede usar un argumento con nombre para realizar la tarea.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 IntelliSense usa corchetes para indicar los parámetros opcionales, tal y como se muestra en la siguiente ilustración.  
  
 ![Información rápida de IntelliSense para el método ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional\_Parameters")  
Parámetros opcionales de ExampleMethod  
  
> [!NOTE]
>  También puede declarar parámetros opcionales mediante la clase <xref:System.Runtime.InteropServices.OptionalAttribute> de .NET.  Los parámetros `OptionalAttribute` no requieren un valor predeterminado.  
  
## Ejemplo  
 En el ejemplo siguiente, el constructor para `ExampleClass` tiene un parámetro, que es opcional.  El método de instancia `ExampleMethod` tiene un parámetro obligatorio, `required`, y dos parámetros opcionales, `optionalstr` y `optionalint`.  El código en `Main` muestra las distintas formas en que se pueden invocar el constructor y el método.  
  
 [!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## Interfaces COM  
 Los argumentos opcionales y con nombre, así como la compatibilidad con los objetos dinámicos y otros avances, mejoran considerablemente la interoperabilidad con las API de COM, como las API de automatización de Office.  
  
 Por ejemplo, el método [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) de la interfaz [Range](http://go.microsoft.com/fwlink/?LinkId=148196) de Microsoft Office Excel tiene siete parámetros, todos ellos opcionales.  Estos parámetros se muestran en la siguiente ilustración.  
  
 ![Información rápida de IntelliSense para el método AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat\_Parameters")  
Parámetros de AutoFormat  
  
 En C\# 3.0 y versiones anteriores, se requiere un argumento para cada parámetro, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 Sin embargo, se puede simplificar considerablemente la llamada a `AutoFormat` utilizando argumentos con nombre y argumentos opcionales, los cuales se incluyen en C\# 4.0.  Los parámetros opcionales y con nombre permiten omitir el argumento de un parámetro opcional si no se desea cambiar el valor predeterminado del parámetro.  En la siguiente llamada, se especifica un valor solamente para uno de los siete parámetros.  
  
 [!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 Para obtener más información y ejemplos, vea [Cómo: Usar argumentos opcionales y con nombre en la programación de Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) y [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
## Resolución de sobrecargas  
 El uso de argumentos opcionales y con nombre afecta a la resolución de sobrecarga de las siguientes formas:  
  
-   Un método, indizador o constructor es candidato para la ejecución si cada uno de sus parámetros es opcional o se corresponde, por nombre o posición, con un argumento único de la instrucción de llamada, y dicho argumento se puede convertir en el tipo del parámetro.  
  
-   Si se encuentra más de un candidato, se aplican reglas de resolución de sobrecarga en relación con las conversiones preferidas a los argumentos especificados explícitamente.  Los argumentos omitidos para los parámetros opcionales se pasan por alto.  
  
-   Si dos candidatos se consideran igualmente buenos, la preferencia recae sobre el candidato que no tiene parámetros opcionales para los que se omitieron argumentos en la llamada.  Esto es consecuencia de una preferencia general en la resolución de sobrecarga por los candidatos con menos parámetros.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Cómo: Usar argumentos opcionales y con nombre en la programación de Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Utilizar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [Utilizar indizadores](../../../csharp/programming-guide/indexers/using-indexers.md)