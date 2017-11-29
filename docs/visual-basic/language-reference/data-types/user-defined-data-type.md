---
title: Tipo de datos definido por el usuario
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e1876d61a2ce89b04c6e5061b868f0be365639f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-data-type"></a>Tipo de datos definido por el usuario
Contiene los datos en un formato que defina. El `Structure` instrucción define el formato.  
  
 Las versiones anteriores de Visual Basic admiten el tipo definido por el usuario (UDT). La versión actual expande el UDT un *estructura*. Una estructura es una concatenación de uno o varios *miembros* de distintos tipos de datos. Visual Basic trata una estructura como una sola unidad, aunque también puede tener acceso a sus miembros individualmente.  
  
## <a name="remarks"></a>Comentarios  
 Definir y usar un tipo de datos de estructura cuando necesite combinar varios tipos de datos en una sola unidad, o cuando ninguno de los tipos de datos básicos satisfaga sus necesidades.  
  
 El valor predeterminado de un tipo de datos de estructura se compone de la combinación de los valores predeterminados de cada uno de sus miembros.  
  
## <a name="declaration-format"></a>Formato de declaración  
 Una declaración de estructura se inicia con la [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md) y termina con el `End``Structure` instrucción. El `Structure` instrucción proporcione el nombre de la estructura, que también es el identificador del tipo de datos es la definición de la estructura. Otras partes del código pueden utilizar este identificador para declarar variables, parámetros y función devuelven valores para que sea del tipo de datos de la estructura.  
  
 Las declaraciones comprendidas entre la `Structure` y `End``Structure` instrucciones definen los miembros de la estructura.  
  
## <a name="member-access-levels"></a>Niveles de acceso de miembro  
 Debe declarar cada miembro utilizando una [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md) o una instrucción que especifica el nivel de acceso, como [público](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../visual-basic/language-reference/modifiers/private.md). Si utiliza un `Dim` instrucción, el acceso a nivel predeterminado es público.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Consumo de memoria.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros. Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración. Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos definidos por el usuario en otros entornos no son compatibles con Visual Basic los tipos de estructuras.  
  
-   **De ampliación.** No hay ninguna conversión automática a o desde cualquier tipo de datos de estructura. Puede definir operadores de conversión en la estructura utilizando el [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md), y se puede declarar cada operador de conversión sea `Widening` o `Narrowing`.  
  
-   **Caracteres de tipo.** Tipos de datos de estructura no tienen ningún carácter de tipo literal ni caracteres de tipo identificador.  
  
-   **Tipo de Framework.** No hay ningún tipo correspondiente en .NET Framework. Todas las estructuras heredan de la clase de .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, pero ninguna estructura individual corresponde a <xref:System.ValueType?displayProperty=nameWithType>.  
  
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
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
