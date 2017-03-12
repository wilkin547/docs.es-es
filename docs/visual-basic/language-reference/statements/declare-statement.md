---
title: "Declare (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Declare"
  - "vb.Lib"
  - "vb.Any"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Alias (palabra clave)"
  - "API, declarar funciones de API"
  - "As (palabra clave), en la instrucción Declare"
  - "declaraciones, externos"
  - "declaraciones, procedimientos"
  - "Declare (instrucción)"
  - "declarar procedimientos, Declare (instrucción)"
  - "DLL, declarar procedimientos"
  - "referencias externas, Visual Basic"
  - "Function (procedimientos), declarar"
  - "funciones [Visual Basic], Function (procedimientos)"
  - "Lib (palabra clave)"
  - "invocación de plataforma, referencias externas de Visual Basic"
  - "procedimientos, declaration"
  - "procedimientos, externos"
  - "Public (palabra clave), Declare (instrucción)"
  - "recursos [Visual Basic], declarar"
  - "Sub (procedimientos), declaraciones"
  - "código de Visual Basic, Function (procedimientos)"
  - "código de Visual Basic, Sub (procedimientos)"
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Declare (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara una referencia a un procedimiento implementado en un archivo externo.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attributelist`|Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional.  Puede ser una de las siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Opcional.  Especifica información sobre el juego de caracteres y la búsqueda de archivos.  Puede ser una de las siguientes:<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) \(valor predeterminado\)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Opcional, pero debe aparecer `Sub` o `Function`.  Indica que el procedimiento externo no devuelve ningún valor.|  
|`Function`|Opcional, pero debe aparecer `Sub` o `Function`.  Indica que el procedimiento externo devuelve un valor.|  
|`name`|Obligatorio.  Nombre de esta referencia externa.  Para obtener más información, vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Obligatorio.  Introduce una cláusula `Lib` que identifica el archivo externo \(archivo DLL o recurso de código\) que contiene un procedimiento externo.|  
|`libname`|Obligatorio.  Nombre del archivo que contiene el procedimiento declarado.|  
|`Alias`|Opcional.  Indica que el procedimiento que se declara no se puede identificar dentro de su archivo mediante el nombre especificado en `name`.  Su identificación se especifica en `aliasname`.|  
|`aliasname`|Es obligatorio si se utiliza la palabra clave `Alias`.  Cadena que identifica el procedimiento en una de estas dos maneras:<br /><br /> Nombre del punto de entrada del procedimiento dentro de su archivo, entre comillas \(`""`\)<br /><br /> O bien<br /><br /> Signo de número \(`#`\) seguido de un entero que especifica el número ordinal del punto de entrada del procedimiento en su archivo|  
|`parameterlist`|Es obligatorio si el procedimiento toma parámetros.  Vea [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Es obligatorio si se especifica `Function` y `Option Strict` tiene el valor `On`.  Tipo de datos del valor devuelto por el procedimiento.|  
  
## Comentarios  
 A veces es necesario llamar a un procedimiento definido en un archivo \(como un archivo DLL o un recurso de código\) fuera del proyecto.  Cuando se hace esto, el compilador de Visual Basic no tiene acceso a la información necesaria para llamar correctamente al procedimiento, por ejemplo dónde está ubicado el procedimiento, cómo se identifica, la secuencia de llamada y el tipo de valor devuelto, y el juego de caracteres de cadena que utiliza.  La instrucción `Declare` crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 Sólo puede utilizar `Declare` en el nivel de módulo.  Esto significa que el *contexto de declaración* de una referencia externa debe ser una clase, estructura o módulo, y no puede ser un archivo de código fuente, espacio de nombres, interfaz, procedimiento o bloque.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Las referencias externas tienen como valor predeterminado el acceso [Public](../../../visual-basic/language-reference/modifiers/public.md).  Puede ajustar sus niveles de acceso con los modificadores de acceso.  
  
## Reglas  
  
-   **Atributos.** Los atributos se pueden aplicar a una referencia externa.  Cualquier atributo que se aplique sólo tiene efecto en su proyecto, no en el archivo externo.  
  
-   **Modificadores.** Los procedimientos externos son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  No se puede utilizar la palabra clave `Shared` al declarar una referencia externa y no se puede modificar su estado compartido.  
  
     Un procedimiento externo no puede participar en operaciones de reemplazar, implementar miembros de interfaz o controlar eventos.  En consecuencia, no se pueden utilizar las palabras clave `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements` o `Handles` en una instrucción `Declare`.  
  
-   **Nombre del procedimiento externo.** No hay que asignar a esta referencia externa \(en `name`\) el mismo nombre que tiene el nombre del punto de entrada del procedimiento en su archivo externo \(`aliasname`\).  Se puede utilizar una cláusula `Alias` para especificar el nombre del punto de entrada.  Esto puede ser útil si el procedimiento externo tiene el mismo nombre que un modificador reservado de Visual Basic o una variable, procedimiento o cualquier otro elemento de programación del mismo ámbito.  
  
    > [!NOTE]
    >  En la mayoría de los archivos DLL, los nombres de punto de entrada distinguen entre mayúsculas y minúsculas.  
  
-   **Número de procedimiento externo.** Alternativamente, se puede utilizar una cláusula `Alias` para especificar el número ordinal del punto de entrada dentro de la tabla de exportación del archivo externo.  Para ello, comience `aliasname` con un signo de número \(`#`\).  Esto puede ser útil si un carácter del nombre de procedimiento externo no se permite en Visual Basic o si el archivo externo exporta el procedimiento sin un nombre.  
  
## Reglas de tipos de datos  
  
-   **Tipos de datos de parámetros.** Si `Option Strict` tiene el valor `On`, se debe especificar el tipo de datos de cada parámetro en `parameterlist`.  Éste puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.  En `parameterlist`, se utiliza una cláusula `As` para especificar el tipo de datos del argumento que se va a pasar a cada parámetro.  
  
    > [!NOTE]
    >  Si el procedimiento externo no se ha escrito para .NET Framework, debe tener cuidado de que los tipos de datos se correspondan.  Por ejemplo, si se declara una referencia externa a un procedimiento de Visual Basic 6.0 con un parámetro `Integer` \(16 bits en Visual Basic 6.0\), el argumento correspondiente debe identificarse como `Short` en la instrucción `Declare`, puesto que es un tipo entero de 16 bits en Visual Basic.  Igualmente, en Visual Basic 6.0 `Long` tiene un ancho de datos diferente y `Date` se implementa de manera diferente.  
  
-   **Tipo de datos devuelto.** Si el procedimiento externo es de tipo `Function` y `Option Strict` tiene el valor `On`, hay que especificar el tipo de datos del valor devuelto al código de llamada.  Éste puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.  
  
    > [!NOTE]
    >  El compilador de Visual Basic no comprueba si los tipos de datos son compatibles con los del procedimiento externo.  Si hay una desigualdad, Common Language Runtime genera una excepción <xref:System.Runtime.InteropServices.MarshalDirectiveException> en tiempo de ejecución.  
  
-   **Tipos de datos predeterminados.** Si `Option Strict` tiene el valor `Off` y no se especifica el tipo de datos de un parámetro en `parameterlist`, el compilador de Visual Basic convierte el argumento correspondiente al [Object \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/object-data-type.md).  Igualmente, si no se especifica `returntype`, el compilador asume que el tipo de datos devuelto es `Object`.  
  
    > [!NOTE]
    >  Como se trata de un procedimiento externo que podría haberse escrito en una plataforma diferente, es peligroso asumir cuál será el tipo de datos o permitir que tomen los valores predeterminados.  Es mucho más seguro especificar el tipo de datos de cada parámetro y del valor devuelto, si se devuelve alguno.  De este modo mejora la legibilidad del código.  
  
## Comportamiento  
  
-   **Ámbito.** Una referencia externa está en ámbito a lo largo de toda su clase, estructura o módulo.  
  
-   **Período de duración.** Una referencia externa tiene el mismo período de duración que la clase, estructura o módulo en las que se declara.  
  
-   **Llamar a un procedimiento externo.** Se puede llamar a un procedimiento externo de la misma manera que se llama a un procedimiento `Function` o `Sub` si se utiliza en una expresión cuando devuelve un valor o si se especifica en [Call \(Instrucción\)](../../../visual-basic/language-reference/statements/call-statement.md) cuando no devuelve un valor.  
  
     Pasa los argumentos al procedimiento externo exactamente como especifica `parameterlist` en la instrucción `Declare`.  No tenga en cuenta cómo se declararon originalmente los parámetros en el archivo externo.  Igualmente, si se devuelve un valor, utilícelo exactamente como especifica `returntype` en la instrucción `Declare`.  
  
-   **Juegos de caracteres.** En `charsetmodifier` se puede especificar cómo Visual Basic debe calcular las referencias de las cadenas cuando se llama al procedimiento externo.  El modificador `Ansi` indica a Visual Basic que calcule las referencias a todas las cadenas como valores ANSI y el modificador `Unicode` le indica que calcule las referencias a todas las cadenas como valores Unicode.  El modificador `Auto` indica a Visual Basic que calcule las referencias a las cadenas según las reglas de .NET Framework basadas en el parámetro `name` de la referencia externa o en el parámetro `aliasname` si se ha especificado.  El valor predeterminado es `Ansi`.  
  
     `charsetmodifier` también especifica la forma en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.  `Ansi` y `Unicode` dirigen Visual Basic a buscarlo sin modificar el nombre durante la búsqueda.  `Auto` dirige Visual Basic para determinar el juego de caracteres base de la plataforma en tiempo de ejecución y posiblemente modificar el nombre de procedimiento externo, como sigue:  
  
    -   En una plataforma ANSI, como Windows 95, Windows 98 o Windows Millennium Edition, busque primero el procedimiento externo sin modificar el nombre.  Si no se encuentra, anexe "A" al final del nombre del procedimiento externo y búsquelo de nuevo.  
  
    -   En una plataforma Unicode, como Windows NT, Windows 2000 o Windows XP, busque primero el procedimiento externo sin modificar el nombre.  Si no se encuentra, anexe "W" al final del nombre del procedimiento externo y búsquelo de nuevo.  
  
-   **Mecanismo.** Visual Basic utiliza el mecanismo de *invocación de plataforma* \(PInvoke\) de .NET Framework para resolver los procedimientos externos y tener acceso a ellos.  La instrucción `Declare` y la clase <xref:System.Runtime.InteropServices.DllImportAttribute> utilizan automáticamente este mecanismo y no es necesario tener conocimientos de PInvoke.  Para obtener más información, vea [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Si el procedimiento externo se ejecuta fuera de Common Language Runtime \(CLR\), es *código no administrado*.  Cuando se llama a este tipo de procedimiento, por ejemplo una función de la API Win32 o un método COM, la aplicación podría quedar expuesta a riesgos de seguridad.  Para obtener más información, vea [Secure Coding Guidelines for Unmanaged Code](../Topic/Secure%20Coding%20Guidelines%20for%20Unmanaged%20Code.md).  
  
## Ejemplo  
 En el ejemplo siguiente se declara una referencia externa a un procedimiento `Function` que devuelve el nombre de usuario actual.  A continuación se llama al procedimiento externo `GetUserNameA` como parte del procedimiento `getUser`.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/declare-statement_1.vb)]  
  
## Ejemplo  
 El atributo <xref:System.Runtime.InteropServices.DllImportAttribute> proporciona otro modo de utilizar funciones en código no administrado.  En el ejemplo siguiente se declara una función importada sin utilizar una instrucción `Declare`.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/declare-statement_3.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Call \(Instrucción\)](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)