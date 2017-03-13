---
title: "Instrucci&#243;n Enum (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Enum"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constantes enumeradas"
  - "Enum (instrucción)"
  - "Private (palabra clave), Enum (instrucciones)"
  - "Public (palabra clave), en la instrucción Enum"
  - "variables [Visual Basic], (enumeración)"
  - "constantes, enumeradas"
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 44
---
# Instrucci&#243;n Enum (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

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
  
     Opcional. Lista de atributos que se aplican a esta enumeración. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) corchetes angulares ("`<`"y"`>`").  
  
     El <xref:System.FlagsAttribute> atributo indica que el valor de una instancia de la enumeración puede incluir varios miembros de enumeración y que cada miembro representa un campo de bits en el valor de enumeración.  
  
-   `accessmodifier`  
  
     Opcional. Especifica qué código puede tener acceso a esta enumeración. Puede ser uno de los siguientes:  
  
    -   [Público](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Privado](../../../visual-basic/language-reference/modifiers/private.md)  
  
     Puede especificar `Protected``Friend` para permitir el acceso desde el código dentro del mismo ensamblado, una clase derivada o clase de enumeración.  
  
-   `Shadows`  
  
     Opcional. Especifica que esta enumeración vuelve a declarar y oculta un elemento de programación denominado de forma idéntica, o un conjunto de elementos sobrecargados, en una clase base. Puede especificar [sombras](../../../visual-basic/language-reference/modifiers/shadows.md) sólo en la propia enumeración, no en cualquiera de sus miembros.  
  
-   `enumerationname`  
  
     Requerido. Nombre de la enumeración. Para obtener información sobre los nombres válidos, consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `datatype`  
  
     Opcional. Tipo de datos de la enumeración y todos sus miembros.  
  
-   `memberlist`  
  
     Requerido. Lista de constantes de miembros que se declara en esta instrucción. Varios miembros aparecen en líneas de código fuente individuales.  
  
     Cada `member` tiene la sintaxis y las partes siguientes: `[<attribute list>] member name [ = initializer ]`  
  
    |||  
    |-|-|  
    |Parte|Descripción|  
    |`membername`|Requerido. Nombre de este miembro.|  
    |`initializer`|Opcional. Expresión que se evalúa en tiempo de compilación y se asigna a este miembro.|  
  
-   `End` `Enum`  
  
     Finaliza el bloque `Enum`.  
  
## <a name="remarks"></a>Comentarios  
 Si tiene un conjunto de valores inalterables que se relacionan lógicamente entre sí, puede definirlos juntos en una enumeración. Esto proporciona nombres descriptivos para la enumeración y sus miembros, que son más fáciles de recordar que sus valores. A continuación, puede utilizar a los miembros de enumeración en muchos lugares en su código.  
  
 Las ventajas de usar las enumeraciones incluyen lo siguiente:  
  
-   Reducir los errores producidos por números transpuestos o.  
  
-   Facilita cambiar los valores en el futuro.  
  
-   Hace el código más fácil de leer, lo que significa que es menos probable que los errores se introducirán.  
  
-   Garantiza la compatibilidad con versiones posteriores. Si utiliza las enumeraciones, su código es menos propenso a errores si en el futuro en que alguien cambia los valores correspondientes a los nombres de miembro.  
  
 Una enumeración tiene un nombre, un tipo de datos subyacente y un conjunto de miembros. Cada miembro representa una constante.  
  
 Una enumeración declarada en el nivel de clase, estructura, módulo o interfaz, fuera de cualquier procedimiento, es un *enumeración de miembros*. Es un miembro de la clase, estructura, módulo o interfaz que la declara.  
  
 Las enumeraciones de miembros pueden obtenerse acceso desde cualquier parte dentro de su clase, estructura, módulo o interfaz. Código fuera de una clase, estructura o módulo debe calificar el nombre de una enumeración de miembros con el nombre de esa clase, estructura o módulo. Puede evitar la necesidad de utilizar nombres completos agregando un [importaciones](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) instrucción al archivo de origen.  
  
 Una enumeración declarada en el nivel de espacio de nombres, fuera de cualquier clase, estructura, módulo o interfaz, es un miembro del espacio de nombres en el que aparece.  
  
 El *contexto de declaración* para una enumeración debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento. Para obtener más información, consulte [contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Se puede aplicar los atributos a una enumeración como un todo, pero no a sus miembros individualmente. Un atributo proporciona información a los metadatos del ensamblado.  
  
## <a name="data-type"></a>Tipo de datos  
 El `Enum` instrucción puede declarar el tipo de datos de una enumeración. Cada miembro toma el tipo de datos de la enumeración. Puede especificar `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort`.  
  
 Si no se especifica `datatype` para la enumeración, cada miembro toma el tipo de datos de su `initializer`. Si se especifican ambas `datatype` y `initializer`, tipo de datos de `initializer` debe poder convertirse a `datatype`. Si no `datatype` ni `initializer` está presente, el valor predeterminado es de tipo de datos `Integer`.  
  
## <a name="initializing-members"></a>Inicialización de miembros  
 El `Enum` instrucción puede inicializar el contenido de los miembros seleccionados en `memberlist`. Utiliza `initializer` para proporcionar una expresión que se asigna al miembro.  
  
 Si no se especifica `initializer` para un miembro, Visual Basic lo inicializa a cero (si es la primera `member` en `memberlist`), o en un valor superior en uno al de la inmediatamente anterior a `member`.  
  
 La expresión proporcionada en cada `initializer` puede ser cualquier combinación de literales, otras constantes que ya están definidas y miembros de enumeración que ya están definidos, incluso un miembro anterior de esta enumeración. Puede utilizar operadores aritméticos y lógicos para combinar estos elementos.  
  
 No puede utilizar variables o funciones en `initializer`. Sin embargo, puede utilizar palabras clave de conversión como `CByte` y `CShort`. También puede utilizar `AscW` Si se le llama con una constante `String` o `Char` argumento, puesto que puede evaluarse en tiempo de compilación.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si un miembro se le asigna un valor de punto flotante y `Option Strict` se establece en on, se produce un error del compilador. Si `Option Strict` está desactivado, el valor se convierte automáticamente en el `Enum` tipo.  
  
 Si el valor de un miembro rebasa el intervalo permitido para el tipo de datos subyacente, o si se inicializa a un miembro al valor máximo permitido por el tipo de datos subyacente, el compilador notifica un error.  
  
## <a name="modifiers"></a>Modificadores  
 Clase, estructura, módulo y predeterminada de enumeraciones de miembro de interfaz acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Espacio de nombres predeterminado de las enumeraciones de miembro para el acceso de confianza. Puede ajustar los niveles de acceso público, pero no a privado o protegido. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Todos los miembros de enumeración tienen acceso público y no puede utilizar ningún modificador de acceso en ellos. Sin embargo, si la propia enumeración tiene un nivel de acceso más limitado, el nivel de acceso de la enumeración especificada tiene prioridad.  
  
 De forma predeterminada, todas las enumeraciones son tipos y sus campos son constantes. Por lo tanto, la `Shared`, `Static`, y `ReadOnly` no se puede usar palabras clave al declarar una enumeración o sus miembros.  
  
## <a name="assigning-multiple-values"></a>Asignar varios valores  
 Enumeraciones suelen representan valores mutuamente exclusivos. Al incluir el <xref:System.FlagsAttribute> atributo el `Enum` declaración, en su lugar, puede asignar varios valores a una instancia de la enumeración. El <xref:System.FlagsAttribute> atributo especifica que la enumeración se tratan como un campo de bits, es decir, un conjunto de indicadores. Se denominan *bit a bit* enumeraciones.  
  
 Cuando se declara una enumeración mediante el uso de la <xref:System.FlagsAttribute> atributo, se recomienda que use potencias de 2, que es, 1, 2, 4, 8, 16 etc., para los valores. También se recomienda que "" ser el nombre de un miembro cuyo valor es 0. Para obtener instrucciones adicionales, consulte <xref:System.FlagsAttribute> y <xref:System.Enum>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `Enum` instrucción. Tenga en cuenta que el miembro se denomina `EggSizeEnum.Medium`, y no como `Medium`.  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 El método en el ejemplo siguiente está fuera de la `Egg` clase. Por lo tanto, `EggSizeEnum` es un nombre completo como `Egg.EggSizeEnum`.  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Enum` denominado de instrucción para definir un conjunto relacionado de valores constantes. En este caso, los valores son colores que puede optar por diseñar formularios de entrada de datos para una base de datos.  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra valores que incluyen números positivos y negativos.  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un `As` cláusula se utiliza para especificar el `datatype` de una enumeración.  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar una enumeración bit a bit. Varios valores se pueden asignar a una instancia de una enumeración bit a bit. El `Enum` declaración incluye la <xref:System.FlagsAttribute> atributo, que indica que la enumeración se puede tratar como un conjunto de indicadores.  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se recorre en iteración una enumeración. Usa el <xref:System.Enum.GetNames%2A> método para recuperar una matriz de nombres de miembro de la enumeración y <xref:System.Enum.GetValues%2A> para recuperar una matriz de valores de miembro.  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Enum>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Funciones de conversión de tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)