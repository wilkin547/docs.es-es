---
title: Declare (instrucción) (Visual Basic)
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
ms.openlocfilehash: 186238d8e823f028caaed2e2618d882d21e1358f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548955"
---
# <a name="declare-statement"></a>Declare Statement
Declara una referencia a un procedimiento implementado en un archivo externo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privado](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private protegida](../../language-reference/modifiers/private-protected.md)<br /><br /> Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Opcional. Especifica el juego de caracteres y el archivo de información de búsqueda. Puede ser uno de los siguientes:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (valor predeterminado)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Automático](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Opcional, pero cualquiera `Sub` o `Function` deben aparecer. Indica que el procedimiento externo no devuelve un valor.|  
|`Function`|Opcional, pero cualquiera `Sub` o `Function` deben aparecer. Indica que el procedimiento externo devuelve un valor.|  
|`name`|Obligatorio. Nombre de esta referencia externa. Para obtener más información, consulte [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Obligatorio. Presenta un `Lib` cláusula que identifica el archivo externo (DLL o recurso de código) que contiene un procedimiento externo.|  
|`libname`|Obligatorio. Nombre del archivo que contiene el procedimiento declarado.|  
|`Alias`|Opcional. Indica que no se puede identificar el procedimiento que se declara dentro de su archivo por el nombre especificado en `name`. Especifique su identificación en `aliasname`.|  
|`aliasname`|Obligatorio si se usa el `Alias` palabra clave. Cadena que identifica el procedimiento de dos maneras:<br /><br /> El nombre del punto de entrada del procedimiento dentro de su archivo entre comillas (`""`)<br /><br /> O bien<br /><br /> Un signo de número (`#`) seguido de un entero que especifica el número ordinal del punto de entrada del procedimiento dentro de su archivo|  
|`parameterlist`|Requerido si el procedimiento toma parámetros. Consulte [Lista_de_parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Es necesario si `Function` se especifica y `Option Strict` es `On`. Tipo de datos del valor devuelto por el procedimiento.|  
  
## <a name="remarks"></a>Comentarios  
 A veces, deberá llamar a un procedimiento definido en un archivo (por ejemplo, un archivo DLL o recurso de código) fuera del proyecto. Al hacerlo, el compilador de Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente, por ejemplo, donde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto y el juego de caracteres de cadena que usa. El `Declare` instrucción crea una referencia a un procedimiento externo y proporciona la información necesaria.  
  
 Solo se puede usar `Declare` en un nivel de módulo. Esto significa que el *contexto de declaración* para una referencia externa debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, el espacio de nombres, la interfaz, el procedimiento o el bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 De forma predeterminada para las referencias externas [pública](../../../visual-basic/language-reference/modifiers/public.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso.  
  
## <a name="rules"></a>Reglas  
  
-   **Atributos.** Puede aplicar atributos a una referencia externa. Cualquier atributo que se aplique tiene efecto solo en el proyecto, no en el archivo externo.  
  
-   **Modificadores.** Procedimientos externos son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md). No puede usar el `Shared` palabra clave cuando se declara una referencia externa y no puede modificar su estado compartido.  
  
     Un procedimiento externo no puede participar en el reemplazo, implementar a miembros de interfaz o controlar los eventos. En consecuencia, no puede usar el `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, o `Handles` palabra clave en un `Declare` instrucción.  
  
-   **Nombre del procedimiento externo.** No es necesario que proporcionar el mismo nombre a esta referencia externa (en `name`) como nombre de punto de entrada del procedimiento en su archivo externo (`aliasname`). Puede usar un `Alias` cláusula para especificar el nombre del punto de entrada. Esto puede ser útil si el procedimiento externo tiene el mismo nombre que un modificador de Visual Basic reservado o una variable, procedimiento o cualquier otro elemento de programación en el mismo ámbito.  
  
    > [!NOTE]
    >  Los nombres de punto de entrada en la mayoría de los archivos DLL distinguen mayúsculas de minúsculas.  
  
-   **Número de procedimiento externo.** Como alternativa, puede usar un `Alias` cláusula para especificar el número ordinal del punto de entrada dentro de la tabla de exportación del archivo externo. Para ello, empezar a `aliasname` con un signo de número (`#`). Esto puede ser útil si no se permite cualquier carácter en el nombre del procedimiento externo en Visual Basic, o si el archivo externo exporta el procedimiento sin nombre.  
  
## <a name="data-type-rules"></a>Reglas de tipo de datos  
  
-   **Tipos de datos de parámetro.** Si `Option Strict` es `On`, debe especificar el tipo de datos de cada parámetro de `parameterlist`. Esto puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz. Dentro de `parameterlist`, usa un `As` cláusula para especificar el tipo de datos del argumento que se pasará a cada parámetro.  
  
    > [!NOTE]
    >  Si el procedimiento externo no se ha escrito para .NET Framework, debe tener cuidado que se corresponden los tipos de datos. Por ejemplo, si declara una referencia externa a un procedimiento de Visual Basic 6.0 con un `Integer` parámetro (16 bits en Visual Basic 6.0), debe identificar el argumento correspondiente como `Short` en el `Declare` instrucción, ya que es 16 - tipo de entero del bit en Visual Basic. De forma similar, `Long` tiene un ancho de datos diferente en Visual Basic 6.0, y `Date` se implementa de manera diferente.  
  
-   **Devolver el tipo de datos.** Si el procedimiento externo es un `Function` y `Option Strict` es `On`, debe especificar el tipo de datos del valor devuelto al código de llamada. Esto puede ser cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.  
  
    > [!NOTE]
    >  El compilador de Visual Basic no comprueba que los tipos de datos sean compatibles con los del procedimiento externo. Si se produce un error de coincidencia, common language runtime genera un <xref:System.Runtime.InteropServices.MarshalDirectiveException> excepción en tiempo de ejecución.  
  
-   **Tipos de datos de forma predeterminada.** Si `Option Strict` es `Off` y no se especifica el tipo de datos de un parámetro en `parameterlist`, el compilador de Visual Basic convierte el argumento correspondiente en el [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md). De forma similar, si no especifica `returntype`, el compilador usa el tipo de datos devuelto sea `Object`.  
  
    > [!NOTE]
    >  Dado que está tratando con un procedimiento externo que es posible que se han escrito en una plataforma diferente, es peligroso para hacer ninguna suposición sobre los tipos de datos o para permitirles en la configuración predeterminada. Es mucho más segura especificar el tipo de datos de cada parámetro y del valor devuelto, si existe. Esto también mejora la legibilidad del código.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Ámbito.** Es una referencia externa en el ámbito de su clase, estructura o módulo.  
  
-   **Duración.** Una referencia externa tiene la misma duración que la clase, estructura o módulo en el que se declara.  
  
-   **Una llamada a un procedimiento externo.** Se llama a un procedimiento externo del mismo modo que se llama a un `Function` o `Sub` procedimiento, si se utiliza en una expresión si devuelve un valor, o si se especifica en un [instrucción Call](../../../visual-basic/language-reference/statements/call-statement.md) si no devuelve un valor.  
  
     Pasar argumentos al procedimiento externo exactamente como se especifica por `parameterlist` en el `Declare` instrucción. No tiene en cuenta cómo los parámetros originalmente se declaran en el archivo externo. De forma similar, si hay un valor devuelto, usarlo exactamente como se especifica por `returntype` en el `Declare` instrucción.  
  
-   **Juegos de caracteres.** Puede especificar en `charsetmodifier` cómo Visual Basic debe serializar las cadenas cuando llama al procedimiento externo. El `Ansi` modificador indica a Visual Basic para calcular las referencias de todas las cadenas como valores ANSI y el `Unicode` modificador dirige a calcular las referencias de todas las cadenas como valores Unicode. El `Auto` modificador indica a Visual Basic para convertir cadenas de acuerdo con .NET Framework, las reglas según la referencia externa `name`, o `aliasname` si se especifica. El valor predeterminado es `Ansi`.  
  
     `charsetmodifier` También especifica cómo Visual Basic debe buscar el procedimiento externo en su archivo externo. `Ansi` y `Unicode` directas Visual Basic para buscar sin modificar su nombre durante la búsqueda. `Auto` indica a Visual Basic para determinar el juego de caracteres de base de la plataforma de tiempo de ejecución y, posiblemente, modifique el nombre del procedimiento externo, como sigue:  
  
    -   En una plataforma de ANSI, como Windows 95, Windows 98 o Windows Millennium Edition, busque primero el procedimiento externo sin modificar el nombre. Si se produce un error, anexe "A" al final del nombre del procedimiento externo y buscar otra vez.  
  
    -   En una plataforma de Unicode, como Windows NT, Windows 2000 o Windows XP, busque primero el procedimiento externo sin modificar el nombre. Si se produce un error, anexe "W" al final del procedimiento externo asigne un nombre y buscar otra vez.  
  
-   **Mecanismo.** Visual Basic utiliza .NET Framework *de invocación de plataforma* mecanismo (PInvoke) para resolver y tener acceso a procedimientos externos. El `Declare` instrucción y el <xref:System.Runtime.InteropServices.DllImportAttribute> clase ambos utilizan este mecanismo automáticamente y no es necesario tener conocimientos de PInvoke. Para obtener más información, vea [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Si el procedimiento externo se ejecuta fuera de common language runtime (CLR), es *código no administrado*. Cuando se llama a este tipo de procedimiento, por ejemplo, una función de la API de Win32 o un método COM, puede exponer su aplicación a riesgos de seguridad. Para obtener más información, consulte [instrucciones de codificación segura para código no administrado](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una referencia externa a una `Function` procedimiento que devuelve el nombre de usuario actual. A continuación, llama el procedimiento externo `GetUserNameA` como parte de la `getUser` procedimiento.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Runtime.InteropServices.DllImportAttribute> proporciona una manera alternativa de utilizar funciones en código no administrado. En el ejemplo siguiente se declara una función importada sin utilizar un `Declare` instrucción.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call (instrucción)](../../../visual-basic/language-reference/statements/call-statement.md)
- [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
