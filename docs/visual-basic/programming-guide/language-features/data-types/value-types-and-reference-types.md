---
title: Tipos de valor y tipos de referencia | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reference data types
- reference types
- value types
- value data types
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: de8016b4b2a5550b32373a41c89a484fa996c596
ms.lasthandoff: 03/13/2017

---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
En Visual Basic, los tipos de datos se implementan según su clasificación. El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipos de datos se pueden clasificar según si una variable de un tipo específico almacena sus propios datos o un puntero a los datos. Si almacena sus propios datos es un *tipo de valor*; si contiene un puntero a datos en otra parte de la memoria es un *tipo de referencia*.  
  
## <a name="value-types"></a>Tipos de valor  
 Un tipo de datos es un *tipo de valor* si almacena los datos en su propia asignación de memoria. Tipos de valor incluyen lo siguiente:  
  
-   Todos los tipos de datos numéricos  
  
-   `Boolean`, `Char` y `Date`  
  
-   Todas las estructuras, incluso si sus miembros son tipos de referencia  
  
-   Las enumeraciones, ya que su tipo subyacente es siempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, o`ULong`  
  
 Cada estructura es un tipo de valor, incluso si contiene a miembros de tipo de referencia. Por este motivo, tipos de valor como `Char` y `Integer` se implementan las estructuras de .NET Framework.  
  
 Puede declarar un tipo de valor mediante la palabra clave reservada de, por ejemplo, `Decimal`. También puede utilizar el `New` palabra clave para inicializar un tipo de valor. Esto es especialmente útil si el tipo tiene un constructor que toma parámetros. Un ejemplo de esto es el <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>constructor, que compila un nuevo `Decimal` el valor de las partes proporcionadas.</xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>  
  
## <a name="reference-types"></a>Tipos de referencia  
 Un *tipo de referencia* contiene un puntero a otra ubicación de memoria que contiene los datos. Tipos de referencia incluyen lo siguiente:  
  
-   `String`  
  
-   Todas las matrices, incluso si sus elementos son tipos de valor  
  
-   Tipos de clase, como<xref:System.Windows.Forms.Form></xref:System.Windows.Forms.Form>  
  
-   Delegados  
  
 Una clase es un *tipo de referencia*. Por este motivo, tipos de referencia como `Object` y `String` admite [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] clases. Observe que cada matriz es un tipo de referencia, incluso si sus miembros son tipos de valor.  
  
 Puesto que cada tipo de referencia representa una clase de .NET Framework subyacente, debe utilizar el [operador New](../../../../visual-basic/language-reference/operators/new-operator.md) palabra clave durante su inicialización. La instrucción siguiente inicializa una matriz.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elementos que no son tipos  
 Los elementos de programación siguientes no se califican como tipos porque no se puede especificar cualquiera de ellos como un tipo de datos para un elemento declarado:  
  
-   Espacios de nombres  
  
-   Módulos  
  
-   Eventos  
  
-   Propiedades y procedimientos  
  
-   Variables, constantes y campos  
  
## <a name="working-with-the-object-data-type"></a>Trabajar con el tipo de datos de objeto  
 Puede asignar un tipo de referencia o un tipo de valor a una variable de la `Object` tipo de datos. Un `Object` variable siempre contiene un puntero a los datos, nunca los propios datos. Sin embargo, si asigna un tipo de valor a un `Object` variable, se comporta como si contuviera sus propios datos. Para obtener más información, consulte [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Puede averiguar si un `Object` variable está actuando como un tipo de referencia o un tipo de valor pasándolo a la <xref:Microsoft.VisualBasic.Information.IsReference%2A>método en la <xref:Microsoft.VisualBasic.Information>clase de la <xref:Microsoft.VisualBasic?displayProperty=fullName>espacio de nombres.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.Information> </xref:Microsoft.VisualBasic.Information.IsReference%2A> <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>Devuelve `True` si el contenido de la `Object` variable representa un tipo de referencia.</xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>Vea también  
 [Tipos de valor que aceptan valores null](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
