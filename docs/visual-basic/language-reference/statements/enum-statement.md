---
title: Instrucción Enum (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: fa97a374d4570e014222bf44844271b3394453da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830076"
---
# <a name="enum-statement-visual-basic"></a>Instrucción Enum (Visual Basic)
Declara una enumeración y define los valores de sus miembros.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a>Elementos  
  
-   `attributelist`  
  
     Opcional. Lista de atributos que se aplican a esta enumeración. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").  
  
     El <xref:System.FlagsAttribute> atributo indica que el valor de una instancia de la enumeración puede incluir varios miembros de enumeración, y que cada miembro representa un campo de bits en el valor de enumeración.  
  
-   `accessmodifier`  
  
     Opcional. Especifica qué código puede tener acceso a esta enumeración. Puede ser uno de los siguientes:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Private Protected](../../language-reference/modifiers/private-protected.md)

-   `Shadows`  
  
     Opcional. Especifica que esta enumeración vuelve a declarar y oculta un elemento de programación con el mismo nombre o el conjunto de elementos sobrecargados, en una clase base. Puede especificar [sombras](../../../visual-basic/language-reference/modifiers/shadows.md) solo en la propia enumeración, no en cualquiera de sus miembros.  
  
-   `enumerationname`  
  
     Obligatorio. Nombre de la enumeración. Para obtener información sobre los nombres válidos, vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `datatype`  
  
     Opcional. Tipo de datos de la enumeración y todos sus miembros.  
  
-   `memberlist`  
  
     Obligatorio. Lista de constantes de miembros que se declaran en esta instrucción. Varios miembros aparecen en líneas de código fuente individuales.  
  
     Cada `member` tiene la sintaxis y las partes siguientes: `[<attribute list>] member name [ = initializer ]`  
  
    |Parte|Descripción|  
    |---|---|  
    |`membername`|Obligatorio. Nombre de este miembro.|  
    |`initializer`|Opcional. Expresión que se evalúa en tiempo de compilación y se asigna a este miembro.|  
  
-   `End` `Enum`  
  
     Finaliza el bloque `Enum`.  
  
## <a name="remarks"></a>Comentarios  
 Si tiene un conjunto de valores inmutables que se relacionan lógicamente entre sí, puede definirlos juntos en una enumeración. Esto proporciona nombres descriptivos para la enumeración y sus miembros, que son más fáciles de recordar que sus valores. A continuación, puede utilizar a los miembros de enumeración en muchos lugares del código.  
  
 Las ventajas de usar las enumeraciones incluyen lo siguiente:  
  
-   Reduce los errores causados por números transpuestos o.  
  
-   Es fácil cambiar los valores en el futuro.  
  
-   Hace el código más fácil de leer, lo que significa que es menos probable que se van a introducir errores.  
  
-   Garantiza la compatibilidad con versiones posteriores. Si utiliza las enumeraciones, el código es menos propenso a errores si en el futuro que alguien cambia los valores correspondientes a los nombres de miembro.  
  
 Una enumeración tiene un nombre, un tipo de datos subyacente y un conjunto de miembros. Cada miembro representa una constante.  
  
 Una enumeración declarada en el nivel de clase, estructura, módulo o interfaz, fuera de cualquier procedimiento, es un *enumeración de miembros*. Es un miembro de la clase, estructura, módulo o interfaz que la declara.  
  
 Las enumeraciones de miembros se pueden acceder desde cualquier lugar dentro de su clase, estructura, módulo o interfaz. Código fuera de una clase, estructura o módulo debe calificar el nombre de una enumeración de miembros con el nombre de esa clase, estructura o módulo. Puede evitar la necesidad de utilizar nombres completos mediante la adición de un [importaciones](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) instrucción al archivo de origen.  
  
 Una enumeración declarada en el nivel de espacio de nombres, fuera de cualquier clase, estructura, módulo o interfaz, es un miembro del espacio de nombres en el que aparece.  
  
 El *contexto de declaración* para una enumeración debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Se puede aplicar los atributos a una enumeración como un todo, pero no a sus miembros individualmente. Un atributo proporciona información a los metadatos del ensamblado.  
  
## <a name="data-type"></a>Tipo de datos  
 El `Enum` instrucción puede declarar el tipo de datos de una enumeración. Cada miembro toma el tipo de datos de la enumeración. Puede especificar `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort`.  
  
 Si no especifica `datatype` para la enumeración, cada miembro toma el tipo de datos de su `initializer`. Si se especifican ambas `datatype` y `initializer`, tipo de datos de `initializer` debe ser convertible a `datatype`. Si no `datatype` ni `initializer` está presente, el valor predeterminado es de tipo de datos `Integer`.  
  
## <a name="initializing-members"></a>Inicialización de miembros  
 El `Enum` instrucción puede inicializar el contenido de los miembros seleccionados en `memberlist`. Usa `initializer` para proporcionar una expresión que se asigna al miembro.  
  
 Si no especifica `initializer` para un miembro, Visual Basic la inicializa a cero (si es la primera `member` en `memberlist`), o en un valor mayor en uno que el de la inmediatamente anterior `member`.  
  
 La expresión proporcionada en cada `initializer` puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos, incluso un miembro anterior de esta enumeración. Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.  
  
 No se puede usar las variables o funciones en `initializer`. Sin embargo, puede usar palabras clave de conversión, como `CByte` y `CShort`. También puede usar `AscW` si se le llama con una constante `String` o `Char` argumento, puesto que puede evaluarse en tiempo de compilación.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si un miembro se le asigna un valor de punto flotante y `Option Strict` se establece en on, se produce un error del compilador. Si `Option Strict` está desactivado, el valor se convierte automáticamente en el `Enum` tipo.  
  
 Si el valor de un miembro supera el intervalo permitido para el tipo de datos subyacente, o si se inicializa a un miembro al valor máximo permitido por el tipo de datos subyacente, el compilador notifica un error.  
  
## <a name="modifiers"></a>Modificadores  
 Clase, estructura, módulo y predeterminado de enumeraciones de miembro de interfaz para acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Namespace predeterminado de enumeraciones de miembro para el acceso de confianza. Puede ajustar sus niveles de acceso público, pero no a privado o protegido. Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Todos los miembros de enumeración tienen acceso público y no se puede usar cualquier modificador de acceso en ellos. Sin embargo, si la propia enumeración tiene un nivel de acceso más restrictivos, el nivel de acceso de la enumeración especificada tiene prioridad.  
  
 De forma predeterminada, todas las enumeraciones son tipos y sus campos son constantes. Por lo tanto, el `Shared`, `Static`, y `ReadOnly` palabras clave no se puede usar cuando se declara una enumeración o sus miembros.  
  
## <a name="assigning-multiple-values"></a>Asignación de varios valores  
 Enumeraciones suelen representan valores mutuamente exclusivos. Al incluir el <xref:System.FlagsAttribute> atributo el `Enum` declaración, en su lugar, puede asignar varios valores a una instancia de la enumeración. El <xref:System.FlagsAttribute> atributo especifica que la enumeración se tratan como un campo de bits, es decir, un conjunto de marcas. Se denominan *bit a bit* enumeraciones.  
  
 Al declarar una enumeración mediante el uso de la <xref:System.FlagsAttribute> atributo, se recomienda que use potencias de 2, que es, 1, 2, 4, 8, 16 y así sucesivamente, para los valores. También se recomienda que "" ser el nombre de un miembro cuyo valor es 0. Para obtener instrucciones adicionales, consulte <xref:System.FlagsAttribute> y <xref:System.Enum>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la instrucción `Enum`. Tenga en cuenta que el miembro se conoce como `EggSizeEnum.Medium`y no como `Medium`.  
  
 [!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]  
  
## <a name="example"></a>Ejemplo  
 El método en el ejemplo siguiente está fuera del `Egg` clase. Por lo tanto, `EggSizeEnum` es un nombre completo como `Egg.EggSizeEnum`.  
  
 [!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Enum` denominado de instrucción para definir un conjunto relacionado de valores constantes. En este caso, los valores son colores que puede optar por diseñar formularios de entrada de datos para una base de datos.  
  
 [!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra los valores que incluyen números positivos y negativos.  
  
 [!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un `As` cláusula se utiliza para especificar el `datatype` de una enumeración.  
  
 [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo utilizar una enumeración bit a bit. Varios valores se pueden asignar a una instancia de una enumeración bit a bit. El `Enum` declaración incluye el <xref:System.FlagsAttribute> atributo, que indica que la enumeración se puede tratar como un conjunto de marcas.  
  
 [!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se recorre en iteración una enumeración. Usa el <xref:System.Enum.GetNames%2A> método para recuperar una matriz de nombres de miembro de la enumeración, y <xref:System.Enum.GetValues%2A> para recuperar una matriz de valores de miembro.  
  
 [!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)
- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)
