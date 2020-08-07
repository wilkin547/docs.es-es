---
title: 'Convenciones de código de C#: Guía de programación de C#'
description: Aprenda sobre las convenciones de código en C#. Las convenciones de código crean una apariencia coherente del código y facilitan la copia, la modificación y el mantenimiento del código.
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 772aebff0b8c7aebe7c7d5c7634cd2931f4570b1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301858"
---
# <a name="c-coding-conventions-c-programming-guide"></a>Convenciones de código de C# (Guía de programación de C#)

Las convenciones de codificación tienen los objetivos siguientes:  
  
- Crean una apariencia coherente en el código, para que los lectores puedan centrarse en el contenido, no en el diseño.  
  
- Permiten a los lectores comprender el código más rápidamente al hacer suposiciones basadas en la experiencia anterior.  
  
- Facilitan la copia, el cambio y el mantenimiento del código.  
  
- Muestran los procedimientos recomendados de C#.  

Microsoft usa las instrucciones de este artículo para desarrollar ejemplos y documentación.  
  
## <a name="naming-conventions"></a>Convenciones de nomenclatura  
  
- En ejemplos breves que no incluyen [directivas using](../../language-reference/keywords/using-directive.md), use calificaciones de espacio de nombres. Si sabe que un espacio de nombres se importa en un proyecto de forma predeterminada, no es necesario completar los nombres de ese espacio de nombres. Los nombres completos pueden partirse después de un punto (.) si son demasiado largos para una sola línea, como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- No es necesario cambiar los nombres de objetos que se crearon con las herramientas del diseñador de Visual Studio para que se ajusten a otras directrices.  
  
## <a name="layout-conventions"></a>Convenciones de diseño  

Un buen diseño utiliza un formato que destaque la estructura del código y haga que el código sea más fácil de leer. Las muestras y ejemplos de Microsoft cumplen las convenciones siguientes:  
  
- Utilice la configuración del Editor de código predeterminada (sangría automática, sangrías de 4 caracteres, tabulaciones guardadas como espacios). Para obtener más información, vea [Opciones, editor de texto, C#, formato](/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
- Escriba solo una instrucción por línea.  
  
- Escriba solo una declaración por línea.  
  
- Si a las líneas de continuación no se les aplica sangría automáticamente, hágalo con una tabulación (cuatro espacios).  
  
- Agregue al menos una línea en blanco entre las definiciones de método y las de propiedad.  
  
- Utilice paréntesis para que las cláusulas de una expresión sean evidentes, como se muestra en el código siguiente.  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a>Convenciones de los comentarios  
  
- Coloque el comentario en una línea independiente, no al final de una línea de código.  
  
- Comience el texto del comentario con una letra mayúscula.  
  
- Finalice el texto del comentario con un punto.  
  
- Inserte un espacio entre el delimitador de comentario (//) y el texto del comentario, como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- No cree bloques con formato de asteriscos alrededor de comentarios.  
  
## <a name="language-guidelines"></a>Convenciones de lenguaje  

En las secciones siguientes se describen las prácticas que sigue el equipo C# para preparar las muestras y ejemplos de código.  
  
### <a name="string-data-type"></a>String (Tipo de datos)  
  
- Use [interpolación de cadenas](../../language-reference/tokens/interpolated.md) para concatenar cadenas cortas, como se muestra en el código siguiente.  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- Para anexar cadenas en bucles, especialmente cuando se trabaja con grandes cantidades de texto, utilice un objeto <xref:System.Text.StringBuilder>.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a>Variables locales con asignación implícita de tipos  
  
- Use [tipos implícitos](../classes-and-structs/implicitly-typed-local-variables.md) para las variables locales cuando el tipo de la variable sea obvio desde el lado derecho de la asignación, o cuando el tipo exacto no sea importante.  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- No use [var](../../language-reference/keywords/var.md) cuando el tipo no sea evidente desde el lado derecho de la asignación.  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- No confíe en el nombre de variable para especificar el tipo de la variable. Puede no ser correcto.  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- Evite el uso de `var` en lugar de [dynamic](../../language-reference/builtin-types/reference-types.md).  
  
- Use tipos implícitos para determinar el tipo de la variable de bucle en bucles [for](../../language-reference/keywords/for.md).  
  
     En el ejemplo siguiente se usan tipos implícitos en una instrucción `for`.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- No use tipos implícitos para determinar el tipo de la variable de bucle en bucles [foreach](../../language-reference/keywords/foreach-in.md).

     En el ejemplo siguiente se usan tipos explícitos en una instrucción `foreach`.

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > Tenga cuidado de no cambiar accidentalmente un tipo de elemento de la colección iterable. Por ejemplo, es fácil cambiar de <xref:System.Linq.IQueryable?displayProperty=nameWithType> a <xref:System.Collections.IEnumerable?displayProperty=nameWithType> en una instrucción `foreach`, lo cual cambia la ejecución de una consulta.

### <a name="unsigned-data-type"></a>Tipo de datos sin signo  
  
En general, utilice `int` en lugar de tipos sin signo. El uso de `int` es común en todo C#, y es más fácil interactuar con otras bibliotecas cuando se usa `int`.  
  
### <a name="arrays"></a>Matrices  
  
Utilice sintaxis concisa para inicializar las matrices en la línea de declaración.  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a>Delegados  
  
Utilice sintaxis concisa para crear instancias de un tipo de delegado.  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>Instrucciones try-catch y using en el control de excepciones  
  
- Use una instrucción [try-catch](../../language-reference/keywords/try-catch.md) en la mayoría de casos de control de excepciones.  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- Simplifique el código mediante la [instrucción using](../../language-reference/keywords/using-statement.md) de C#. Si tiene una instrucción [try-finally](../../language-reference/keywords/try-finally.md) en la que el único código del bloque `finally` es una llamada al método <xref:System.IDisposable.Dispose%2A>, use en su lugar una instrucción `using`.  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a>Operadores && y &#124;&#124;  
  
Para evitar excepciones y aumentar el rendimiento omitiendo las comparaciones innecesarias, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) en lugar de [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) y [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) en lugar de [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) cuando realice comparaciones, como se muestra en el ejemplo siguiente.  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a>New (Operador)  
  
- Utilice la forma concisa de la creación de instancias de objeto con tipos implícitos, como se muestra en la siguiente declaración.  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     La línea anterior es equivalente a la siguiente declaración.  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- Utilice inicializadores de objeto para simplificar la creación de objetos.  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a>Control de eventos  
  
Si va a definir un controlador de eventos que no es necesario quitar más tarde, utilice una expresión lambda.  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a>Miembros estáticos  
  
Llame a miembros [estáticos](../../language-reference/keywords/static.md) con el nombre de clase: *ClassName.StaticMember*. Esta práctica hace que el código sea más legible al clarificar el acceso estático.  No califique un miembro estático definido en una clase base con el nombre de una clase derivada.  Mientras el código se compila, su legibilidad se presta a confusión, y puede interrumpirse en el futuro si se agrega a un miembro estático con el mismo nombre a la clase derivada.  
  
### <a name="linq-queries"></a>Consultas LINQ  
  
- Utilice nombres descriptivos para las variables de consulta. En el ejemplo siguiente, se utiliza `seattleCustomers` para los clientes que se encuentran en Seattle.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Utilice alias para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente con mayúscula o minúscula, usando para ello la grafía Pascal.  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado. Por ejemplo, si la consulta devuelve un nombre de cliente y un identificador de distribuidor, en lugar de dejarlos como `Name` e `ID` en el resultado, cambie su nombre para aclarar que `Name` es el nombre de un cliente e `ID` es el identificador de un distribuidor.  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- Utilice tipos implícitos en la declaración de variables de consulta y variables de intervalo.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Alinee las cláusulas de consulta bajo la cláusula [from](../../language-reference/keywords/from-clause.md), como se muestra en los ejemplos anteriores.  
  
- Use cláusulas [where](../../language-reference/keywords/where-clause.md) antes de otras cláusulas de consulta para asegurarse de que las cláusulas de consulta posteriores operan en un conjunto de datos reducido y filtrado.  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- Use varias cláusulas `from` en lugar de una cláusula [join](../../language-reference/keywords/join-clause.md) para obtener acceso a colecciones internas. Por ejemplo, una colección de objetos `Student` podría contener cada uno un conjunto de resultados de exámenes. Cuando se ejecuta la siguiente consulta, devuelve cada resultado superior a 90, además del apellido del alumno que recibió la puntuación.  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a>Seguridad  

Siga las instrucciones de [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md).  
  
## <a name="see-also"></a>Consulte también

- [Convenciones de código de Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md)
