---
title: Declare Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2560f34a5130ef7453b50ffb4495b67bf1dfa4c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
|`attributelist`|Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Público](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`charsetmodifier`|Opcional. Especifica el juego de caracteres y el archivo de información de búsqueda. Puede ser uno de los siguientes:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (valor predeterminado)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Automático](../../../visual-basic/language-reference/modifiers/auto.md)|  
|`Sub`|Opcional, pero cualquiera `Sub` o `Function` deben aparecer. Indica que el procedimiento externo no devuelve ningún valor.|  
|`Function`|Opcional, pero cualquiera `Sub` o `Function` deben aparecer. Indica que el procedimiento externo devuelve un valor.|  
|`name`|Obligatorio. Nombre de esta referencia externa. Para obtener más información, consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Lib`|Obligatorio. Presenta un `Lib` cláusula, que identifica el archivo externo (DLL o recurso de código) que contiene un procedimiento externo.|  
|`libname`|Obligatorio. Nombre del archivo que contiene el procedimiento declarado.|  
|`Alias`|Opcional. Indica que no se puede identificar el procedimiento que se declara dentro de su archivo por el nombre especificado en `name`. Especifique su identificación en `aliasname`.|  
|`aliasname`|Es obligatorio si se utiliza la `Alias` (palabra clave). Cadena que identifica el procedimiento en uno de dos maneras:<br /><br /> El nombre de punto de entrada del procedimiento dentro de su archivo entre comillas (`""`)<br /><br /> O bien<br /><br /> Un signo de número (`#`) seguido de un entero que especifica el número ordinal del punto de entrada del procedimiento dentro de su archivo|  
|`parameterlist`|Necesario si el procedimiento toma parámetros. Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`returntype`|Obligatorio si `Function` se especifica y `Option Strict` es `On`. Tipo de datos del valor devuelto por el procedimiento.|  
  
## <a name="remarks"></a>Comentarios  
 A veces es necesario llamar a un procedimiento definido en un archivo (por ejemplo, un archivo DLL o recurso de código) fuera del proyecto. Al hacerlo, el compilador de Visual Basic no tiene acceso a la información que necesita para llamar correctamente al procedimiento, por ejemplo, donde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto y el juego de caracteres de cadena que utiliza. El `Declare` instrucción crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 Solo se puede usar `Declare` en un nivel de módulo. Esto significa que la *contexto de la declaración* para una referencia externa debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, espacio de nombres, interfaz, procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 De forma predeterminada para las referencias externas [público](../../../visual-basic/language-reference/modifiers/public.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso.  
  
## <a name="rules"></a>Reglas  
  
-   **Atributos.** Puede aplicar atributos a una referencia externa. Cualquier atributo que se aplique tiene efecto solo en el proyecto, no en el archivo externo.  
  
-   **Modificadores.** Procedimientos externos son implícitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md). No se puede utilizar el `Shared` palabra clave al declarar una referencia externa y no puede modificar su estado compartido.  
  
     Un procedimiento externo no puede participar en el reemplazo, implementar a miembros de interfaz o controlar los eventos. En consecuencia, no puede usar el `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, o `Handles` palabra clave en un `Declare` instrucción.  
  
-   **Nombre del procedimiento externo.** No es necesario dar el mismo nombre de esta referencia externa (en `name`) como nombre de punto de entrada del procedimiento en su archivo externo (`aliasname`). Puede usar un `Alias` cláusula para especificar el nombre de punto de entrada. Esto puede ser útil si el procedimiento externo tiene el mismo nombre que un modificador reservado de Visual Basic o una variable, procedimiento o cualquier otro elemento de programación en el mismo ámbito.  
  
    > [!NOTE]
    >  Nombres de punto de entrada en la mayoría de las DLL distinguen entre mayúsculas y minúsculas.  
  
-   **Número de procedimiento externo.** Como alternativa, puede usar un `Alias` cláusula para especificar el número ordinal del punto de entrada en la tabla de exportación del archivo externo. Para ello, comenzar `aliasname` con un signo de número (`#`). Esto puede ser útil si cualquier carácter en el nombre del procedimiento externo no se permite en Visual Basic, o si el archivo externo exporta el procedimiento sin un nombre.  
  
## <a name="data-type-rules"></a>Reglas de tipo de datos  
  
-   **Tipos de datos de parámetro.** Si `Option Strict` es `On`, debe especificar el tipo de datos de cada parámetro en `parameterlist`. Esto puede ser cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración. Dentro de `parameterlist`, utiliza un `As` cláusula para especificar el tipo de datos del argumento que se pasará a cada parámetro.  
  
    > [!NOTE]
    >  Si el procedimiento externo no se ha escrito para .NET Framework, debe tener cuidado que corresponden los tipos de datos. Por ejemplo, si declara una referencia externa a un procedimiento de Visual Basic 6.0 con un `Integer` parámetro (16 bits en Visual Basic 6.0), debe identificar el argumento correspondiente como `Short` en la `Declare` (instrucción), ya que es 16 - tipo de entero del bit en Visual Basic. De forma similar, `Long` tiene un ancho de datos diferente en Visual Basic 6.0, y `Date` se implementan de forma diferente.  
  
-   **Devuelve el tipo de datos.** Si el procedimiento externo es un `Function` y `Option Strict` es `On`, debe especificar el tipo de datos del valor devuelto al código de llamada. Esto puede ser cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.  
  
    > [!NOTE]
    >  El compilador de Visual Basic no comprueba que los tipos de datos son compatibles con los del procedimiento externo. Si se produce un error de coincidencia, common language runtime genera un <xref:System.Runtime.InteropServices.MarshalDirectiveException> excepción en tiempo de ejecución.  
  
-   **Tipos de datos predeterminados.** Si `Option Strict` es `Off` y no se especifica el tipo de datos de un parámetro de `parameterlist`, el compilador de Visual Basic convierte el argumento correspondiente en el [tipo de datos de objeto](../../../visual-basic/language-reference/data-types/object-data-type.md). De forma similar, si no se especifica `returntype`, el compilador usa el tipo de datos devuelto sea `Object`.  
  
    > [!NOTE]
    >  Dado que está tratando con un procedimiento externo que podría haberse escrito en una plataforma diferente, es peligroso para hacer ninguna suposición acerca de los tipos de datos o para permitir que tomen los valores predeterminados. Es mucho más seguro especificar el tipo de datos de cada parámetro y el valor devuelto, si existe. Esto también mejora la legibilidad del código.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Ámbito.** Una referencia externa está en ámbito a lo largo de su clase, estructura o módulo.  
  
-   **Duración.** Una referencia externa tiene la misma duración que la clase, estructura o módulo en el que se declara.  
  
-   **Llamar a un procedimiento externo.** Se llama a un procedimiento externo del mismo modo que se llama a un `Function` o `Sub` procedimiento: si se utiliza en una expresión cuando devuelve un valor, o si se especifica en un [instrucción Call](../../../visual-basic/language-reference/statements/call-statement.md) si no devuelve un valor.  
  
     Pasar argumentos al procedimiento externo exactamente tal y como especifica `parameterlist` en el `Declare` instrucción. No tiene en cuenta cómo se declararon originalmente los parámetros en el archivo externo. De forma similar, si hay un valor devuelto, usarlo exactamente tal y como especifica `returntype` en el `Declare` instrucción.  
  
-   **Conjuntos de caracteres.** Puede especificar en `charsetmodifier` cómo Visual Basic debe calcular las referencias de cadenas cuando llama al procedimiento externo. El `Ansi` modificador indica a Visual Basic para calcular las referencias de todas las cadenas a valores ANSI y la `Unicode` modificador dirige al calcular las referencias de todas las cadenas a valores Unicode. El `Auto` modificador indica a Visual Basic para calcular referencias de cadenas según .NET Framework reglas en función de la referencia externa `name`, o `aliasname` si se especifica. El valor predeterminado es `Ansi`.  
  
     `charsetmodifier`También especifica cómo Visual Basic debe buscar el procedimiento externo en su archivo externo. `Ansi`y `Unicode` ambos indican a Visual Basic que se buscará sin modificar su nombre durante la búsqueda. `Auto`indica a Visual Basic para determinar el juego de caracteres base de la plataforma de tiempo de ejecución y posiblemente modificar el nombre del procedimiento externo, como se indica a continuación:  
  
    -   En una plataforma ANSI, como Windows 95, Windows 98 o Windows Millennium Edition, busque primero el procedimiento externo sin modificar el nombre. Si se produce un error, anexar "A" al final del nombre del procedimiento externo y búsquelo de nuevo.  
  
    -   En una plataforma Unicode, como Windows NT, Windows 2000 o Windows XP, busque primero el procedimiento externo sin modificar el nombre. Si eso no funciona, anexe "W" al final del procedimiento externo asigne un nombre y buscar otra vez.  
  
-   **Mecanismo.** Visual Basic utiliza .NET Framework *de invocación de plataforma* mecanismo (PInvoke) para resolver y tener acceso a un procedimiento externo. El `Declare` instrucción y la <xref:System.Runtime.InteropServices.DllImportAttribute> clase ambos usan este mecanismo automáticamente y no es necesario tener conocimientos de PInvoke. Para obtener más información, consulte [Tutorial: llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
> [!IMPORTANT]
>  Si el procedimiento externo se ejecuta fuera de common language runtime (CLR), es *código no administrado*. Cuando se llama a este tipo de procedimiento, por ejemplo, una función de la API de Win32 o un método COM, puede exponer su aplicación a riesgos de seguridad. Para obtener más información, consulte [instrucciones de codificación segura para código no administrado](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una referencia externa a un `Function` procedimiento que devuelve el nombre del usuario actual. A continuación, llama al procedimiento externo `GetUserNameA` como parte de la `getUser` procedimiento.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Runtime.InteropServices.DllImportAttribute> proporciona una manera alternativa de utilizar las funciones en código no administrado. En el ejemplo siguiente se declara una función importada sin utilizar un `Declare` instrucción.  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Call (instrucción)](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
