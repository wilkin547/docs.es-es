---
title: Declare Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 9895709076634ce156ba9d1009f79ba7ddd2ba56
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646383"
---
# <a name="declare-statement"></a>Declare Statement

Declara una referencia a un procedimiento implementado en un archivo externo.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`attributelist`|Opcional. Consulte [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Público](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Amigo](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privado](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Amigo protegido](../../language-reference/modifiers/protected-friend.md)<br />- [Protegido privado](../../language-reference/modifiers/private-protected.md)<br /><br /> Consulte Niveles de [acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Opcional. Consulte [Sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|
|`charsetmodifier`|Opcional. Especifica el juego de caracteres y la información de búsqueda de archivos. Puede ser uno de los siguientes:<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) (predeterminado)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Automático](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|Opcional, pero `Sub` `Function` debe aparecer o debe aparecer. Indica que el procedimiento externo no devuelve un valor.|
|`Function`|Opcional, pero `Sub` `Function` debe aparecer o debe aparecer. Indica que el procedimiento externo devuelve un valor.|
|`name`|Necesario. Nombre de esta referencia externa. Para obtener más información, vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Necesario. Introduce una `Lib` cláusula, que identifica el archivo externo (DLL o recurso de código) que contiene un procedimiento externo.|
|`libname`|Necesario. Nombre del archivo que contiene el procedimiento declarado.|
|`Alias`|Opcional. Indica que el procedimiento que se declara no se puede `name`identificar dentro de su archivo por el nombre especificado en . Especifique su identificación en `aliasname`.|
|`aliasname`|Necesario si utiliza `Alias` la palabra clave. Cadena que identifica el procedimiento de una de estas dos maneras:<br /><br /> El nombre del punto de entrada del`""`procedimiento dentro de su archivo, entre comillas ( )<br /><br /> o bien<br /><br /> Un signo`#`numérico ( ) seguido de un entero que especifica el número ordinal del punto de entrada del procedimiento dentro de su archivo|
|`parameterlist`|Necesario si el procedimiento toma parámetros. Consulte [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|
|`returntype`|Necesario `Function` si se `Option Strict` especifica `On`y es . Tipo de datos del valor devuelto por el procedimiento.|

## <a name="remarks"></a>Observaciones

A veces es necesario llamar a un procedimiento definido en un archivo (como un archivo DLL o un recurso de código) fuera del proyecto. Al hacerlo, el compilador de Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente, como dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el conjunto de caracteres de cadena que usa. La `Declare` instrucción crea una referencia a un procedimiento externo y proporciona esta información necesaria.

Solo se puede usar `Declare` en un nivel de módulo. Esto significa que el contexto de *declaración* para una referencia externa debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, espacio de nombres, interfaz, procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Las referencias externas tienen como valor predeterminado [Acceso público.](../../../visual-basic/language-reference/modifiers/public.md) Los niveles de acceso se pueden ajustar con los modificadores de acceso.

## <a name="rules"></a>Reglas

- **Atributos.** Puede aplicar atributos a una referencia externa. Cualquier atributo que aplique solo tiene efecto en el proyecto, no en el archivo externo.

- **Modificadores.** Los procedimientos externos se [comparten](../../../visual-basic/language-reference/modifiers/shared.md)implícitamente. No puede `Shared` utilizar la palabra clave al declarar una referencia externa y no puede modificar su estado compartido.

  Un procedimiento externo no puede participar en la invalidación, implementar miembros de interfaz o controlar eventos. En consecuencia, no `Overrides`puede `Overridable` `NotOverridable`utilizar `MustOverride` `Implements`la `Handles` palabra clave `Declare` , , , , , , en una instrucción.

- **Nombre del procedimiento externo.** No es necesario asignar a esta referencia `name`externa el mismo nombre (en ) que`aliasname`el nombre de punto de entrada del procedimiento dentro de su archivo externo ( ). Puede utilizar `Alias` una cláusula para especificar el nombre de punto de entrada. Esto puede ser útil si el procedimiento externo tiene el mismo nombre que un modificador reservado de Visual Basic o una variable, procedimiento o cualquier otro elemento de programación en el mismo ámbito.

  > [!NOTE]
  > Los nombres de punto de entrada en la mayoría de los archivos DLL distinguen mayúsculas de minúsculas.

- **Número de procedimiento externo.** Como alternativa, puede `Alias` utilizar una cláusula para especificar el número ordinal del punto de entrada dentro de la tabla de exportación del archivo externo. Para ello, comience `aliasname` con un`#`signo numérico ( ). Esto puede ser útil si no se permite ningún carácter en el nombre del procedimiento externo en Visual Basic, o si el archivo externo exporta el procedimiento sin un nombre.

## <a name="data-type-rules"></a>Reglas de tipo de datos

- **Tipos de datos de parámetros.** Si `Option Strict` `On`es , debe especificar el tipo `parameterlist`de datos de cada parámetro en . Puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz. Dentro `parameterlist`de , `As` se utiliza una cláusula para especificar el tipo de datos del argumento que se pasará a cada parámetro.

  > [!NOTE]
  > Si el procedimiento externo no se ha escrito para .NET Framework, debe tener cuidado de que los tipos de datos correspondan. Por ejemplo, si declara una referencia externa a un `Integer` procedimiento de Visual Basic 6.0 con un parámetro (16 bits en Visual Basic 6.0), debe identificar el argumento correspondiente como `Short` en la `Declare` instrucción, porque es el tipo entero de 16 bits en Visual Basic. De `Long` forma similar, tiene un ancho de `Date` datos diferente en Visual Basic 6.0 y se implementa de forma diferente.

- **Tipo de datos de devolución.** Si el procedimiento `Function` externo `Option Strict` `On`es a y es , debe especificar el tipo de datos del valor devuelto al código de llamada. Puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.

  > [!NOTE]
  > El compilador de Visual Basic no comprueba que los tipos de datos son compatibles con los del procedimiento externo. Si hay una discordancia, Common <xref:System.Runtime.InteropServices.MarshalDirectiveException> Language Runtime genera una excepción en tiempo de ejecución.

- **Tipos de datos predeterminados.** Si `Option Strict` `Off` es y no especifica el tipo `parameterlist`de datos de un parámetro en , el compilador de Visual Basic convierte el argumento correspondiente en el tipo de datos de [objeto](../../../visual-basic/language-reference/data-types/object-data-type.md). De forma similar, `returntype`si no especifica , el `Object`compilador toma el tipo de datos devuelto como .

  > [!NOTE]
  > Dado que está tratando con un procedimiento externo que podría haberse escrito en una plataforma diferente, es peligroso realizar suposiciones sobre tipos de datos o permitir que se preentras se deben realizar. Es mucho más seguro especificar el tipo de datos de cada parámetro y del valor devuelto, si existe. Esto también mejora la legibilidad del código.

## <a name="behavior"></a>Comportamiento

- **Ámbito.** Una referencia externa está en el ámbito a lo largo de su clase, estructura o módulo.

- **Vida.** Una referencia externa tiene la misma duración que la clase, estructura o módulo en el que se declara.

- **Llamar a un procedimiento externo.** Se llama a un procedimiento externo `Function` `Sub` de la misma manera que se llama a un procedimiento o, utilizándolo en una expresión si devuelve un valor, o especificándolo en una [instrucción Call](../../../visual-basic/language-reference/statements/call-statement.md) si no devuelve un valor.

  Los argumentos se pasan al procedimiento `parameterlist` externo `Declare` exactamente como se especifica en la instrucción. No tenga en cuenta cómo se declararon originalmente los parámetros en el archivo externo. De forma similar, si hay un valor devuelto, utilícelo exactamente como se especifica en `returntype` la `Declare` instrucción.

- **Conjuntos de caracteres.** Puede especificar `charsetmodifier` en cómo Visual Basic debe calcular las referencias de cadenas cuando llama al procedimiento externo. El `Ansi` modificador indica a Visual Basic que haga de `Unicode` la serialización de todas las cadenas en valores ANSI y el modificador le indica que haga las referencias de todas las cadenas a valores Unicode. El `Auto` modificador indica a Visual Basic que haga las referencias `name`de `aliasname` cadenas según las reglas de .NET Framework basadas en la referencia externa o, si se especifica. El valor predeterminado es `Ansi`.

  `charsetmodifier`También especifica cómo Visual Basic debe buscar el procedimiento externo dentro de su archivo externo. `Ansi`y `Unicode` ambos dirigen a Visual Basic para buscarlo sin modificar su nombre durante la búsqueda. `Auto`indica a Visual Basic que determine el conjunto de caracteres base de la plataforma en tiempo de ejecución y, posiblemente, modifique el nombre del procedimiento externo, como se indica a continuación:

  - En una plataforma ANSI, como Windows 95, Windows 98 o Windows Millennium Edition, primero busque el procedimiento externo sin modificar el nombre. Si se produce un error, anexe "A" al final del nombre del procedimiento externo y búsquelo de nuevo.

  - En una plataforma Unicode, como Windows NT, Windows 2000 o Windows XP, primero busque el procedimiento externo sin modificación de nombre. Si se produce un error, anexe "W" al final del nombre del procedimiento externo y búsquelo de nuevo.

- **Mecanismo.** Visual Basic usa el mecanismo de *invocación* de plataforma (PInvoke) de .NET Framework para resolver y tener acceso a procedimientos externos. La `Declare` instrucción <xref:System.Runtime.InteropServices.DllImportAttribute> y la clase utilizan este mecanismo automáticamente y no necesita ningún conocimiento de PInvoke. Para obtener más información, vea [Tutorial: llamar a las API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)de Windows .

> [!IMPORTANT]
> Si el procedimiento externo se ejecuta fuera de Common Language Runtime (CLR), es *código no administrado.* Cuando se llama a un procedimiento de este tipo, por ejemplo, una función de API de Windows o un método COM, puede exponer la aplicación a riesgos de seguridad. Para obtener más información, consulte Directrices de [codificación segura para código no administrado](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se `Function` declara una referencia externa a un procedimiento que devuelve el nombre de usuario actual. A continuación, llama `GetUserNameA` al procedimiento `getUser` externo como parte del procedimiento.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Ejemplo

Proporciona <xref:System.Runtime.InteropServices.DllImportAttribute> una forma alternativa de usar funciones en código no administrado. En el ejemplo siguiente se declara `Declare` una función importada sin utilizar una instrucción.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AddressOf Operador](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Instrucción Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Instrucción Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Instrucción Call](../../../visual-basic/language-reference/statements/call-statement.md)
- [Tutorial: Llamadas a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
