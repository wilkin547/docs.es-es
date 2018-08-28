---
title: Tipo de datos definido por el usuario (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 1dac93145b6e11a0d149f03b43e1e0b28b770925
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003181"
---
# <a name="user-defined-data-type"></a>Tipo de datos definido por el usuario
Contiene los datos en un formato que defina. El `Structure` instrucción define el formato.  
  
 Las versiones anteriores de Visual Basic admiten el tipo definido por el usuario (UDT). La versión actual expande el UDT un *estructura*. Una estructura es una concatenación de uno o varios *miembros* de diversos tipos de datos. Visual Basic trata una estructura como una sola unidad, aunque también puede tener acceso a sus miembros individualmente.  
  
## <a name="remarks"></a>Comentarios  
 Definir y usar un tipo de datos de estructura cuando necesite combinar varios tipos de datos en una sola unidad, o cuando ninguno de los tipos de datos elementales atender sus necesidades.  
  
 El valor predeterminado de un tipo de datos de estructura se compone de la combinación de los valores predeterminados de cada uno de sus miembros.  
  
## <a name="declaration-format"></a>Formato de declaración  
 Una declaración structure comienza con la [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md) y termina con la `End Structure` instrucción. El `Structure` instrucción proporciona el nombre de la estructura, que también es el identificador del tipo de datos consiste en definir la estructura. Otras partes del código pueden utilizar este identificador para declarar variables, parámetros y función devuelven valores para que sea del tipo de datos de esta estructura.  
  
 Las declaraciones de entre el `Structure` y `End Structure` instrucciones definen los miembros de la estructura.  
  
## <a name="member-access-levels"></a>Niveles de acceso de miembro  
 Debe declarar cada miembro utilizando un [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md) o una instrucción que especifica el nivel de acceso, tales como [pública](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../visual-basic/language-reference/modifiers/private.md). Si usa un `Dim` instrucción, los valores predeterminados nivel de acceso público.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Consumo de memoria.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros. Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración. Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.  
  
-   **Consideraciones de interoperabilidad.** Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos definidos por el usuario en otros entornos no son compatibles con Visual Basic los tipos de estructuras.  
  
-   **Ampliación.** No hay ninguna conversión automática a o desde cualquier tipo de datos de estructura. Puede definir operadores de conversión en la estructura utilizando el [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md), y se puede declarar cada operador de conversión se `Widening` o `Narrowing`.  
  
-   **Caracteres de tipo.** Tipos de datos de estructura no tienen ningún carácter de tipo literal o un carácter de tipo identificador.  
  
-   **Tipo de marco de trabajo.** No hay ningún tipo correspondiente en .NET Framework. Todas las estructuras heredan de la clase de .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, pero ninguna estructura individual que corresponde a <xref:System.ValueType?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 El paradigma siguiente muestra el esquema de la declaración de una estructura.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
