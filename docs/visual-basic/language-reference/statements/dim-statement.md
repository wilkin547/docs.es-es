---
title: Instrucción Dim (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234732"
---
# <a name="dim-statement-visual-basic"></a>Instrucción Dim (Visual Basic)
Declara y asigna espacio de almacenamiento para una o más variables.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>Elementos  
  
-   `attributelist`  
  
     Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Privado protegido](../../language-reference/modifiers/private-protected.md)

     Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Opcional. Vea [compartido](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Opcional. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Opcional. Vea [estático](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Opcional. Vea [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Opcional. Especifica que se trata de variables de objeto que hacen referencia a instancias de una clase que puede provocar eventos. Vea [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Requerido. Lista de variables que se declaran en esta instrucción.  
  
     `variable [ , variable ... ]`  
  
     Cada `variable` tiene la sintaxis y las partes siguientes:  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Parte|Descripción|  
    |---|---|  
    |`variablename`|Requerido. Nombre de la variable. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Opcional. Lista de límites de cada dimensión de una variable de matriz.|  
    |`New`|Opcional. Crea una nueva instancia de la clase cuando la `Dim` instrucción se ejecuta.|  
    |`datatype`|Opcional. Tipo de datos de la variable.|  
    |`With`|Opcional. Presenta la lista de inicializadores de objeto.|  
    |`propertyname`|Opcional. El nombre de una propiedad en la clase que se está realizando una instancia de.|  
    |`propinitializer`|Necesario después `propertyname` =. La expresión que se evalúa y se asigna al nombre de propiedad.|  
    |`initializer`|Opcional si `New` no se ha especificado. Expresión que se evalúa y se asigna a la variable cuando se crea.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador de Visual Basic utiliza la `Dim` instrucción para determinar el tipo de datos de la variable y otra información, como qué código puede tener acceso a la variable. En el ejemplo siguiente se declara una variable que contenga una `Integer` valor.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 Puede especificar cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Para un tipo de referencia, utilice el `New` palabra clave para crear una nueva instancia de la clase o estructura que se especifica por el tipo de datos. Si utiliza `New`, no utiliza una expresión de inicializador. En su lugar, que proporcione los argumentos, si es necesarios, al constructor de la clase desde el que está creando la variable.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 Puede declarar una variable en una clase, estructura, procedimiento, bloque o módulo. No se puede declarar una variable en un archivo de código fuente, el espacio de nombres o la interfaz. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Una variable que se declara en el nivel de módulo, fuera de cualquier procedimiento, es un *variable miembro* o *campo*. Las variables de miembro están en ámbito a lo largo de su clase, estructura o módulo. Una variable que se declara en el nivel de procedimiento es un *variable local*. Las variables locales están en ámbito solo dentro de su procedimiento o bloque.  
  
 Los modificadores de acceso siguientes se usan para declarar variables fuera de un procedimiento: `Public`, `Protected`, `Friend`, `Protected Friend`, y `Private`. Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El `Dim` palabra clave es opcional y normalmente se omite si se especifica cualquiera de los siguientes modificadores: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, o `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Si `Option Explicit` es on (valor predeterminado), el compilador requiere una declaración para cada variable que se utiliza. Para obtener más información, consulte [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Especificar un valor inicial  
 Puede asignar un valor a una variable cuando se crea. Para un tipo de valor, utilice un *inicializador* para proporcionar una expresión que se asignará a la variable. La expresión debe evaluarse como una constante que se puede calcular en tiempo de compilación.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Si se especifica un inicializador y no se especifica un tipo de datos en un `As` cláusula, *inferencia de tipo* se usa para inferir el tipo de datos desde el inicializador. En el ejemplo siguiente, ambos `num1` y `num2` están fuertemente tipados como enteros. En la segunda declaración, inferencia de tipo deduce el tipo del valor 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 Inferencia de tipo se aplica en el nivel de procedimiento. No se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz. Para obtener más información acerca de la inferencia de tipo, consulte [Option Infer instrucción](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Para obtener información sobre lo que ocurre cuando no se especifica un tipo de datos o un inicializador, consulte [valores y tipos de datos predeterminados](../../../visual-basic/language-reference/statements/dim-statement.md#default) más adelante en este tema.  
  
 Puede usar un *inicializador de objeto* para declarar instancias de tipos con nombre y anónimos. El código siguiente crea una instancia de un `Student` clase y usa un inicializador de objeto para inicializar las propiedades.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Para obtener más información sobre los inicializadores de objeto, vea [Cómo: declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [inicializadores de objeto: tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), y [tipos anónimos ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Declarar varias Variables  
 Puede declarar varias variables en una instrucción de declaración, especificando el nombre de variable para cada uno de ellos y después de cada nombre de matriz con paréntesis. Las variables se separan con comas.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Si se declara más de una variable con una `As` cláusula, no puede proporcionar un inicializador para el grupo de variables.  
  
 Puede especificar los tipos de datos diferentes para distintas variables mediante otro `As` cláusula para cada variable que se declara. Cada variable toma el tipo de datos especificado en la primera `As` cláusula encontró después de su `variablename` parte.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Matrices  
 Puede declarar una variable que contenga una *matriz*, que puede contener varios valores. Para especificar que una variable contiene una matriz, siga su `variablename` inmediatamente con paréntesis. Para obtener más información acerca de las matrices, vea [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Puede especificar los límites inferior y superior de cada dimensión de una matriz. Para hacerlo, incluya un `boundslist` dentro de los paréntesis. Para cada dimensión, el `boundslist` especifica el límite superior y, opcionalmente, el límite inferior. El límite inferior es siempre cero, si se especifica o no. Cada índice puede variar de cero a su valor de límite superior.  
  
 Las dos instrucciones siguientes son equivalentes. Cada instrucción declara una matriz de 21 `Integer` elementos. Cuando tiene acceso a la matriz, el índice puede variar entre 0 y 20.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 La siguiente instrucción declara una matriz bidimensional de tipo `Double`. La matriz tiene 4 filas (3 + 1) de 6 columnas (5 + 1) cada una. Tenga en cuenta que un límite superior representa el mayor valor posible para el índice, no la longitud de la dimensión. La longitud de la dimensión es el límite superior más uno.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Una matriz puede tener de 1 a 32 dimensiones.  
  
 Puede dejar en blanco en una declaración de matriz de todos los límites. Si lo hace, la matriz tiene el número de dimensiones especificadas, pero no está inicializado. Tiene un valor de `Nothing` hasta que se inicialicen al menos algunos de sus elementos. El `Dim` instrucción debe especificar límites para todas las dimensiones o para ninguna dimensión.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Si la matriz tiene más de una dimensión, debe incluir comas entre paréntesis para indicar el número de dimensiones.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 Puede declarar un *matriz de longitud cero* declarando una de las dimensiones de la matriz sea -1. Una variable que contiene una matriz de longitud cero no tiene el valor `Nothing`. Matrices de longitud cero son necesarios para determinadas funciones de common language runtime. Si intenta tener acceso a dicha matriz, se produce una excepción en tiempo de ejecución. Para obtener más información, consulte [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Puede inicializar los valores de una matriz mediante un literal de matriz. Para ello, incluya los valores de inicialización con llaves (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Para las matrices multidimensionales, la inicialización de cada dimensión se encierra entre llaves en la dimensión exterior. Los elementos se especifican en orden de importancia de filas.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Para obtener más información sobre los literales de matriz, vea [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
##  <a name="default"></a> Tipos de datos predeterminados y valores  
 En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.  
  
|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|  
|---|---|---|---|  
|No|No|`Dim qty`|Si [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) es off (valor predeterminado), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|No|Sí|`Dim qty = 5`|Si [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) es on (valor predeterminado), escriba la variable toma los datos del inicializador. Vea [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos. Vea la tabla más adelante en esta sección.|  
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|  
  
 Si especifica un tipo de datos pero no especifica a un inicializador, Visual Basic inicializa la variable en el valor predeterminado para su tipo de datos. En la tabla siguiente muestra el valor predeterminado de los valores de inicialización.  
  
|Tipo de datos|Valor predeterminado|  
|---|---|  
|Todos los tipos numéricos (incluidos `Byte` y `SByte`)|0|  
|`Char`|0 binario|  
|Todos los tipos de referencia (incluidos `Object`, `String`y todas las matrices)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|12:00 A.M. del 1 de enero del año 1 (01/01/0001 12:00:00 A.M.)|  
  
 Cada elemento de una estructura se inicializa como si fuera una variable independiente. Si se declara la longitud de una matriz pero no se inicializan sus elementos, cada elemento se inicializa como si fuera una variable independiente.  
  
## <a name="static-local-variable-lifetime"></a>Duración de la Variable Local estática  
 Un `Static` variable local tiene una duración más larga que el procedimiento en el que se declara. Dependen de los límites de duración de la variable donde se declara el procedimiento y si es `Shared`.  
  
|Declaración de procedimiento|Variable inicializada|Detiene la variable existente|  
|---|---|---|  
|En un módulo|La primera vez que se llama al procedimiento|Cuando detiene la ejecución del programa|  
|En una clase o estructura, el procedimiento es `Shared`|La primera vez que se llama al procedimiento en una instancia específica o en la propia clase o estructura|Cuando detiene la ejecución del programa|  
|En una clase o estructura, no es el procedimiento `Shared`|La primera vez que se llama al procedimiento en una instancia específica|Cuando se libera la instancia para la recopilación de elementos no utilizados (GC)|  
  
## <a name="attributes-and-modifiers"></a>Los atributos y modificadores  
 Puede aplicar atributos solo a variables de miembro, no a las variables locales. Un atributo proporciona información a los metadatos del ensamblado, que no son significativos para el almacenamiento temporal como las variables locales.  
  
 En el nivel de módulo, no puede usar el `Static` modificador para declarar las variables de miembro. En el nivel de procedimiento, no puede usar `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, o cualquier acceso modificadores para declarar variables locales.  
  
 Puede especificar qué código puede tener acceso a una variable proporcionando un `accessmodifier`. Clase y módulo predeterminado de variables (fuera de cualquier procedimiento) miembro a acceso privado y predeterminada de las variables de miembro de estructura para acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso. No puede usar los modificadores de acceso en variables locales (dentro de un procedimiento).  
  
 Puede especificar `WithEvents` solo en variables de miembro, no en variables locales dentro de un procedimiento. Si especifica `WithEvents`, el tipo de datos de la variable debe ser un tipo de clase concreto, no `Object`. No se puede declarar una matriz con `WithEvents`. Para obtener más información acerca de los eventos, vea [eventos](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Código fuera de una clase, estructura o módulo debe calificar el nombre de la variable de miembro con el nombre de esa clase, estructura o módulo. El código fuera de que un procedimiento o bloque no puede hacer referencia a cualquier variable local dentro de ese procedimiento o bloque.  
  
## <a name="releasing-managed-resources"></a>Liberar los recursos administrados  
 El recolector de elementos no utilizados de .NET Framework se deshace de los recursos administrados sin necesidad de código adicional por su parte. Sin embargo, puede forzar la eliminación de un recurso administrado en lugar de esperar el recolector de elementos no utilizados.  
  
 Si una clase se bloquea en un recurso especialmente valioso y escaso (por ejemplo, un identificador de conexión o el archivo de base de datos), no puede esperar hasta la siguiente recolección para limpiar una instancia de clase que ya no está en uso. Una clase puede implementar la <xref:System.IDisposable> interfaz para proporcionar una manera para liberar los recursos antes de una colección de elementos no utilizados. Una clase que implementa esa interfaz expone un `Dispose` método que se puede llamar para forzar valiosos recursos se libera inmediatamente.  
  
 El `Using` instrucción automatiza el proceso de adquisición de un recurso, ejecutar un conjunto de instrucciones y, a continuación, elimine el recurso. Sin embargo, debe implementar el recurso de la <xref:System.IDisposable> interfaz. Para obtener más información, vea [Using (Instrucción)](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara variables mediante el `Dim` instrucción con varias opciones.  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se enumeran los números primos entre 1 y 30. El ámbito de las variables locales se describe en los comentarios del código.  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la `speedValue` variable se declara en el nivel de clase. El `Private` palabra clave se utiliza para declarar la variable. La variable puede tener acceso a todos los procedimientos en el `Car` clase.  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
 [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Option Infer (instrucción)](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
