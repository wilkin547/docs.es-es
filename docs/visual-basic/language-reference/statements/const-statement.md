---
title: Instrucción Const (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 089c2dca99373f379e1eff319cf8c41242e5f135
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835315"
---
# <a name="const-statement-visual-basic"></a>Instrucción Const (Visual Basic)
Declara y define una o varias constantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Lista de atributos que se aplican a todas las constantes se declara en esta instrucción. Consulte [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").  
  
 `accessmodifier`  
 Opcional. Se usa para especificar qué código puede tener acceso a estas constantes. Puede ser [pública](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [privada](../../../visual-basic/language-reference/modifiers/private.md), o [Private protegida](../../language-reference/modifiers/private-protected.md).
  
 `Shadows`  
 Opcional. Utilícelo para volver a declarar y ocultar un elemento de programación en una clase base. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Obligatorio. Lista de constantes que se declaran en esta instrucción.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Cada `constant` tiene la sintaxis y las partes siguientes:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Parte|Descripción|  
|----------|-----------------|  
|`constantname`|Obligatorio. Nombre de la constante. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Es necesario si `Option Strict` es `On`. Tipo de datos de la constante.|  
|`initializer`|Obligatorio. Expresión que se evalúa en tiempo de compilación y se asigna a la constante.|  
  
## <a name="remarks"></a>Comentarios  
 Si tiene un valor que nunca cambia en la aplicación, puede definir una constante con nombre y usarlo en lugar de un valor literal. Un nombre es más fácil de recordar que un valor. Puede definir la constante de una sola vez y usarlo en muchos lugares del código. Si en una versión posterior tiene que volver a definir el valor, el `Const` instrucción es el único lugar donde tiene que realizar un cambio.  
  
 Puede usar `Const` sólo en el nivel de módulo o un procedimiento. Esto significa que el *contexto de declaración* para una variable debe ser de clase, estructura, módulo, procedimiento o bloque y no puede ser un archivo de código fuente, el espacio de nombres o la interfaz. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Valor predeterminado de las constantes locales (dentro de un procedimiento) acceso público y no puede usar cualquier modificador de acceso en ellos. Módulo y clase miembro constantes (fuera de cualquier procedimiento) de forma predeterminada a acceso privado y estructura miembros constantes como valor predeterminado para el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de declaración.** Una constante declarada en el nivel de módulo, fuera de cualquier procedimiento, es un *constante miembro*; es un miembro de la clase, estructura o módulo que lo declara.  
  
     Una constante declarada en el nivel de procedimiento es un *constante local*; éste es local para el procedimiento o bloque que lo declara.  
  
-   **Atributos.** Puede aplicar atributos solo a las constantes de miembro, no a las constantes locales. Un atributo proporciona información a los metadatos del ensamblado, que no son significativos para el almacenamiento temporal como constantes locales.  
  
-   **Modificadores.** De forma predeterminada, todas las constantes son `Shared`, `Static`, y `ReadOnly`. No se puede usar cualquiera de estas palabras clave al declarar una constante.  
  
     En el nivel de procedimiento, no puede usar `Shadows` o cualquier acceso modificadores para declarar constantes locales.  
  
-   **Varias constantes.** Puede declarar varias constantes en la misma instrucción de declaración, especificando el `constantname` parte para cada uno de ellos. Varias constantes están separadas por comas.  
  
## <a name="data-type-rules"></a>Reglas de tipo de datos  
  
-   **Tipos de datos.** El `Const` instrucción puede declarar el tipo de datos de una variable. Puede especificar cualquier tipo de datos o el nombre de una enumeración.  
  
-   **Tipo predeterminado.** Si no especifica `datatype`, la constante tiene el tipo de datos del `initializer`. Si se especifican ambas `datatype` y `initializer`, tipo de datos de `initializer` debe ser convertible a `datatype`. Si no `datatype` ni `initializer` está presente, el valor predeterminado es de tipo de datos `Object`.  
  
-   **Diferentes tipos.** Puede especificar los tipos de datos diferentes para distintas constantes utilizando otro `As` cláusula para cada variable que declare. Sin embargo, no se puede declarar varias constantes para que sea del mismo tipo mediante un común `As` cláusula.  
  
-   **Inicialización.** Debe inicializar el valor de cada constante en `constantlist`. Usa `initializer` para proporcionar una expresión que se asignará a la constante. La expresión puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos. Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.  
  
     No se puede usar las variables o funciones en `initializer`. Sin embargo, puede usar palabras clave de conversión, como `CByte` y `CShort`. También puede usar `AscW` si se le llama con una constante `String` o `Char` argumento, puesto que puede evaluarse en tiempo de compilación.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Ámbito.** Constantes locales solo son accesibles desde dentro de su procedimiento o bloque. Constantes de miembro son accesibles desde cualquier lugar dentro de su clase, estructura o módulo.  
  
-   **Calificación.** Código fuera de una clase, estructura o módulo debe calificar el nombre de una constante de miembro con el nombre de esa clase, estructura o módulo. Fuera de que un procedimiento o bloque no puede hacer referencia a una de estas constantes local dentro de ese procedimiento o bloque de código.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Const` instrucción para declarar constantes para su uso en lugar de valores literales.  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a>Ejemplo  
 Si define una constante con el tipo de datos `Object`, el compilador de Visual Basic proporciona el tipo de `initializer`, en lugar de `Object`. En el ejemplo siguiente, la constante `naturalLogBase` tiene el tipo de tiempo de ejecución `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 El ejemplo anterior utiliza la <xref:System.Type.ToString%2A> método en el <xref:System.Type> objeto devuelto por la [GetType (operador)](../../../visual-basic/language-reference/operators/gettype-operator.md), porque <xref:System.Type> no se puede convertir a `String` mediante `CStr`.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)
- [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)
- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Constantes y enumeraciones](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
