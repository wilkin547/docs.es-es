---
description: 'Más información sobre: declare (instrucción)'
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
ms.openlocfilehash: 8ad8169515bbb2889c0adbed4df4e30a0215d47d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673848"
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
|`attributelist`|Opcional. Vea [lista de atributos](attribute-list.md).|
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Pública](../modifiers/public.md)<br />-   [Contra](../modifiers/protected.md)<br />-   [Respecto](../modifiers/friend.md)<br />-   [Privada](../modifiers/private.md)<br />- [Friend protegido](../modifiers/protected-friend.md)<br />- [Privado protegido](../modifiers/private-protected.md)<br /><br /> Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Opcional. Vea [Shadows](../modifiers/shadows.md).|
|`charsetmodifier`|Opcional. Especifica el juego de caracteres y la información de búsqueda de archivos. Puede ser uno de los siguientes:<br /><br /> -   [ANSI](../modifiers/ansi.md) (valor predeterminado)<br />-   [Unicode](../modifiers/unicode.md)<br />-   [Automático](../modifiers/auto.md)|
|`Sub`|Opcional, pero `Sub` `Function` debe aparecer o. Indica que el procedimiento externo no devuelve un valor.|
|`Function`|Opcional, pero `Sub` `Function` debe aparecer o. Indica que el procedimiento externo devuelve un valor.|
|`name`|Necesario. Nombre de esta referencia externa. Para obtener más información, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Necesario. Introduce una `Lib` cláusula, que identifica el archivo externo (dll o recurso de código) que contiene un procedimiento externo.|
|`libname`|Necesario. Nombre del archivo que contiene el procedimiento declarado.|
|`Alias`|Opcional. Indica que no se puede identificar el procedimiento declarado en su archivo por el nombre especificado en `name` . Especifique su identificación en `aliasname` .|
|`aliasname`|Obligatorio si se usa la `Alias` palabra clave. Cadena que identifica el procedimiento de una de estas dos maneras:<br /><br /> Nombre del punto de entrada del procedimiento dentro de su archivo, entre comillas ( `""` )<br /><br /> o bien<br /><br /> Un signo de número ( `#` ) seguido de un entero que especifica el número ordinal del punto de entrada del procedimiento dentro de su archivo.|
|`parameterlist`|Obligatorio si el procedimiento toma parámetros. Vea [lista de parámetros](parameter-list.md).|
|`returntype`|Obligatorio si `Function` se especifica y `Option Strict` es `On` . Tipo de datos del valor devuelto por el procedimiento.|

## <a name="remarks"></a>Observaciones

A veces es necesario llamar a un procedimiento definido en un archivo (por ejemplo, un archivo DLL o un recurso de código) fuera del proyecto. Al hacerlo, el compilador Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente, como dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa. La `Declare` instrucción crea una referencia a un procedimiento externo y proporciona esta información necesaria.

Solo se puede usar `Declare` en un nivel de módulo. Esto significa que el contexto de la *declaración* de una referencia externa debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Las referencias externas tienen como valor predeterminado el acceso [público](../modifiers/public.md) . Los niveles de acceso se pueden ajustar con los modificadores de acceso.

## <a name="rules"></a>Reglas

- **Sus.** Puede aplicar atributos a una referencia externa. Cualquier atributo que aplique solo tiene efecto en el proyecto, no en el archivo externo.

- **Modificadores.** Los procedimientos externos se [comparten](../modifiers/shared.md)implícitamente. No se puede usar la `Shared` palabra clave al declarar una referencia externa y no se puede modificar su estado compartido.

  Un procedimiento externo no puede participar en la invalidación, la implementación de miembros de interfaz o la administración de eventos. En consecuencia, no se puede usar la `Overrides` `Overridable` `NotOverridable` palabra clave,,,, `MustOverride` `Implements` o `Handles` en una `Declare` instrucción.

- **Nombre del procedimiento externo.** No es necesario asignar a esta referencia externa el mismo nombre (en `name` ) que el nombre de punto de entrada del procedimiento dentro de su archivo externo ( `aliasname` ). Puede usar una `Alias` cláusula para especificar el nombre del punto de entrada. Esto puede ser útil si el procedimiento externo tiene el mismo nombre que un modificador Visual Basic reservado o una variable, un procedimiento o cualquier otro elemento de programación en el mismo ámbito.

  > [!NOTE]
  > Los nombres de punto de entrada en la mayoría de los archivos dll distinguen mayúsculas de minúsculas.

- **Número de procedimiento externo.** Como alternativa, puede usar una `Alias` cláusula para especificar el número ordinal del punto de entrada en la tabla de exportación del archivo externo. Para ello, empiece `aliasname` por un signo de número ( `#` ). Esto puede ser útil si no se permite ningún carácter en el nombre del procedimiento externo en Visual Basic, o si el archivo externo exporta el procedimiento sin un nombre.

## <a name="data-type-rules"></a>Reglas de tipo de datos

- **Tipos de datos de parámetros.** Si `Option Strict` es `On` , debe especificar el tipo de datos de cada parámetro en `parameterlist` . Puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz. En `parameterlist` , se usa una `As` cláusula para especificar el tipo de datos del argumento que se va a pasar a cada parámetro.

  > [!NOTE]
  > Si el procedimiento externo no se escribió para el .NET Framework, debe tener cuidado de que los tipos de datos se correspondan. Por ejemplo, si declara una referencia externa a un procedimiento Visual Basic 6,0 con un `Integer` parámetro (16 bits en Visual Basic 6,0), debe identificar el argumento correspondiente como `Short` en la `Declare` instrucción, ya que es el tipo entero de 16 bits en Visual Basic. De forma similar, `Long` tiene un ancho de datos diferente en Visual Basic 6,0 y `Date` se implementa de forma diferente.

- **Tipo de datos devuelto.** Si el procedimiento externo es `Function` y `Option Strict` es `On` , debe especificar el tipo de datos del valor que se devuelve al código de llamada. Puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.

  > [!NOTE]
  > El compilador Visual Basic no comprueba si los tipos de datos son compatibles con los del procedimiento externo. Si hay un error de coincidencia, el Common Language Runtime genera una <xref:System.Runtime.InteropServices.MarshalDirectiveException> excepción en tiempo de ejecución.

- **Tipos de datos predeterminados.** Si `Option Strict` es `Off` y no se especifica el tipo de datos de un parámetro en `parameterlist` , el compilador Visual Basic convierte el argumento correspondiente al [tipo de datos del objeto](../data-types/object-data-type.md). Del mismo modo, si no se especifica `returntype` , el compilador toma el tipo de datos devuelto `Object` .

  > [!NOTE]
  > Dado que está tratando con un procedimiento externo que puede haberse escrito en una plataforma diferente, es peligroso realizar suposiciones sobre los tipos de datos o para permitir que se conviertan en valores predeterminados. Es mucho más seguro especificar el tipo de datos de cada parámetro y del valor devuelto, si hay alguno. Esto también mejora la legibilidad del código.

## <a name="behavior"></a>Comportamiento

- **Ámbito.** Una referencia externa está en el ámbito a lo largo de su clase, estructura o módulo.

- **Validez.** Una referencia externa tiene la misma duración que la clase, estructura o módulo en el que se declara.

- **Llamar a un procedimiento externo.** Se llama a un procedimiento externo del mismo modo que se llama a un `Function` `Sub` procedimiento o; para ello, se usa en una expresión, si devuelve un valor, o si se especifica en una [instrucción de llamada](call-statement.md) si no devuelve un valor.

  Los argumentos se pasan al procedimiento externo exactamente como se especifica `parameterlist` en en la `Declare` instrucción. No tenga en cuenta cómo se declararon originalmente los parámetros en el archivo externo. De forma similar, si hay un valor devuelto, úselo exactamente como se especifica `returntype` en la `Declare` instrucción.

- **Juegos de caracteres.** Puede especificar en `charsetmodifier` qué Visual Basic debe serializar las cadenas cuando llama al procedimiento externo. El `Ansi` modificador dirige Visual Basic para calcular las referencias de todas las cadenas a valores ANSI y el `Unicode` modificador le indica que calcule las referencias de todas las cadenas a valores Unicode. El `Auto` modificador dirige Visual Basic para calcular las referencias de cadenas según las reglas de .NET Framework basadas en la referencia externa `name` , o `aliasname` si se especifica. El valor predeterminado es `Ansi`.

  `charsetmodifier` también especifica el modo en que Visual Basic debe buscar el procedimiento externo en su archivo externo. `Ansi` y `Unicode` ambas Visual Basic directas para buscarla sin modificar su nombre durante la búsqueda. `Auto` dirige Visual Basic para determinar el juego de caracteres base de la plataforma en tiempo de ejecución y posiblemente modificar el nombre del procedimiento externo, como se indica a continuación:

  - En una plataforma ANSI, como Windows 95, Windows 98 o Windows Millennium Edition, primero debe buscar el procedimiento externo sin modificar el nombre. Si se produce un error, anexe "a" al final del nombre del procedimiento externo y búsquelo de nuevo.

  - En una plataforma Unicode, como Windows NT, Windows 2000 o Windows XP, primero debe buscar el procedimiento externo sin modificar el nombre. Si se produce un error, anexe "W" al final del nombre del procedimiento externo y búsquelo de nuevo.

- **Método.** Visual Basic utiliza el mecanismo de *invocación de plataforma* .NET Framework (PInvoke) para resolver y tener acceso a procedimientos externos. La `Declare` instrucción y la <xref:System.Runtime.InteropServices.DllImportAttribute> clase usan este mecanismo automáticamente y no se necesita ningún conocimiento de PInvoke. Para obtener más información, consulte [Tutorial: llamar a las API de Windows](../../programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Si el procedimiento externo se ejecuta fuera del Common Language Runtime (CLR), se trata de *código no administrado*. Cuando llame a este procedimiento, por ejemplo, una función de la API de Windows o un método COM, podría exponer la aplicación a riesgos de seguridad. Para obtener más información, vea [instrucciones de codificación segura para código no administrado](/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara una referencia externa a un `Function` procedimiento que devuelve el nombre de usuario actual. A continuación, llama al procedimiento externo `GetUserNameA` como parte del `getUser` procedimiento.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Ejemplo

<xref:System.Runtime.InteropServices.DllImportAttribute>Proporciona una forma alternativa de usar funciones en código no administrado. En el ejemplo siguiente se declara una función importada sin utilizar una `Declare` instrucción.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](imports-statement-net-namespace-and-type.md)
- [Operador AddressOf](../operators/addressof-operator.md)
- [Instrucción Function](function-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Lista de parámetros](parameter-list.md)
- [Instrucción Call](call-statement.md)
- [Tutorial: Llamadas a las API de Windows](../../programming-guide/com-interop/walkthrough-calling-windows-apis.md)
