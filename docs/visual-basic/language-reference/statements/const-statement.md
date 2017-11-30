---
title: "Instrucción Const (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Const
helpviewer_keywords: Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 720a465f1459b663a1fca2a48856f51762328459
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
 Opcional. Lista de atributos que se aplican a todas las constantes declaradas en esta instrucción. Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) corchetes angulares ("`<`"y"`>`").  
  
 `accessmodifier`  
 Opcional. Se usa para especificar qué código puede tener acceso a estas constantes. Puede ser [público](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, o [privada](../../../visual-basic/language-reference/modifiers/private.md).  
  
 `Shadows`  
 Opcional. Utilícelo para volver a declarar y ocultar un elemento de programación en una clase base. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Obligatorio. Lista de constantes que se declaran en esta instrucción.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Cada `constant` tiene la sintaxis y las partes siguientes:  
  
 `constantname``[ As``datatype``] =``initializer`  
  
|Parte|Descripción|  
|----------|-----------------|  
|`constantname`|Obligatorio. Nombre de la constante. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Obligatorio si `Option Strict` es `On`. Tipo de datos de la constante.|  
|`initializer`|Obligatorio. Expresión que se evalúa en tiempo de compilación y se asigna a la constante.|  
  
## <a name="remarks"></a>Comentarios  
 Si tiene un valor que nunca cambia en la aplicación, puede definir una constante con nombre y utilizarlo en lugar de un valor literal. Un nombre es más fácil de recordar que un valor. Puede definir la constante sólo una vez y utilizar en muchos lugares en el código. Si en una versión posterior necesita volver a definir el valor, la `Const` instrucción es el único lugar necesita realizar un cambio.  
  
 Puede usar `Const` sólo en el nivel de módulo o procedimiento. Esto significa que la *contexto de la declaración* para una variable debe ser una clase, estructura, módulo, procedimiento o bloque y no puede ser un archivo de código fuente, el espacio de nombres o la interfaz. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Valor predeterminado de constantes locales (dentro de un procedimiento) para acceso público y no puede usar modificadores de acceso en ellos. Clase y módulo predeterminado de constantes (fuera de cualquier procedimiento) miembro a acceso privado y estructura miembros constantes como valor predeterminado para el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Una constante declarada en el nivel de módulo, fuera de cualquier procedimiento, es un *constante de miembro*; es un miembro de la clase, estructura o módulo que lo declara.  
  
     Una constante declarada en el nivel de procedimiento es un *constante local*; éste es local para el procedimiento o un bloque que lo declara.  
  
-   **Atributos.** Puede aplicar atributos solo a las constantes de miembro, no a las constantes locales. Un atributo proporciona información a los metadatos del ensamblado, que no son significativos para el almacenamiento temporal como constantes locales.  
  
-   **Modificadores.** De forma predeterminada, todas las constantes son `Shared`, `Static`, y `ReadOnly`. No se puede usar cualquiera de estas palabras clave al declarar una constante.  
  
     En el nivel de procedimiento, no puede utilizar `Shadows` o cualquier acceso modificadores para declarar constantes locales.  
  
-   **Varias constantes.** Puede declarar varias constantes en la misma instrucción de declaración, especificando la `constantname` parte para cada uno de ellos. Constantes múltiples se separan por comas.  
  
## <a name="data-type-rules"></a>Reglas de tipo de datos  
  
-   **Tipos de datos.** El `Const` instrucción puede declarar el tipo de datos de una variable. Puede especificar cualquier tipo de datos o el nombre de una enumeración.  
  
-   **Tipo predeterminado.** Si no se especifica `datatype`, la constante toma el tipo de datos de `initializer`. Si se especifican ambas `datatype` y `initializer`, tipo de datos de `initializer` debe poder convertirse a `datatype`. Si no `datatype` ni `initializer` está presente, el valor predeterminado es de tipo de datos `Object`.  
  
-   **Tipos diferentes.** Puede especificar los tipos de datos diferentes para distintas constantes mediante otro `As` cláusula para cada variable que se declara. Sin embargo, no puede declarar varias constantes para que sea del mismo tipo mediante una común `As` cláusula.  
  
-   **Inicialización.** Debe inicializar el valor de cada constante en `constantlist`. Utiliza `initializer` para proporcionar una expresión que se asignará a la constante. La expresión puede ser cualquier combinación de literales, otras constantes que ya se han definido y miembros de enumeración que ya se han definido. Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.  
  
     No se puede utilizar variables o funciones en `initializer`. Sin embargo, puede usar palabras clave de conversión como `CByte` y `CShort`. También puede usar `AscW` si se le llama con una constante `String` o `Char` argumento, puesto que puede evaluarse en tiempo de compilación.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Ámbito.** Constantes locales son accesibles únicamente desde dentro de su procedimiento o bloque. Constantes de miembro son accesibles desde cualquier lugar dentro de su clase, estructura o módulo.  
  
-   **Calificación.** Código fuera de una clase, estructura o módulo debe calificar el nombre de una constante de miembro con el nombre de esa clase, estructura o módulo. El código fuera de que un procedimiento o bloque no puede hacer referencia a ninguna constante local dentro de ese procedimiento o bloque.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Const` instrucción para declarar constantes para su uso en lugar de valores literales.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Si define una constante con el tipo de datos `Object`, el compilador de Visual Basic proporciona el tipo de `initializer`, en lugar de `Object`. En el ejemplo siguiente, la constante `naturalLogBase` tiene el tipo de tiempo de ejecución `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 El ejemplo anterior utiliza la <xref:System.Type.ToString%2A> método en el <xref:System.Type> objeto devuelto por la [GetType (operador)](../../../visual-basic/language-reference/operators/gettype-operator.md), porque <xref:System.Type> no se puede convertir a `String` con `CStr`.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Constantes y enumeraciones](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
