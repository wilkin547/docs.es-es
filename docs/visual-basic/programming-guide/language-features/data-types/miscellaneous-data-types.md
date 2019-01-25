---
title: Tipos de datos variados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 7e32bf158b91c23c32028eb6877bd0089a9019b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655054"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipos de datos variados (Visual Basic)
Visual Basic proporciona varios tipos de datos que no están orientados a números o caracteres. En su lugar, tratan con datos especializados, como sí/no valores, valores de fecha y hora y las direcciones del objeto.  
  
 Para una tabla que muestra una comparación en paralelo de los tipos de datos de Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Tipo booleano  
 El [tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) es un valor sin signo que se interpreta como `True` o `False`. El ancho de datos depende de la plataforma de implementación. Si una variable puede contener sólo valores de dos estados como verdadero/falso, sí/no o activado/desactivado, declárelo como `Boolean`.  
  
## <a name="date-type"></a>Tipo de fecha  
 El [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene información de fecha y hora. Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el principio (12:00 A.M.) del 1 de enero del año 1 del calendario gregoriano. Si una variable puede contener un valor de fecha, un valor de hora o ambas, declárelo como `Date`.  
  
## <a name="object-type"></a>Tipo de objeto  
 El [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) es una dirección de 32 bits que señala a una instancia de objeto dentro de la aplicación o en otra aplicación. Un `Object` variable puede hacer referencia a cualquier objeto de la aplicación reconozca, o a datos de cualquier tipo de datos. Esto incluye tanto *los tipos de valor*, tales como `Integer`, `Boolean`e instancias de estructura, y *hacen referencia a tipos*, que son instancias de objetos creados a partir de clases como `String`y <xref:System.Windows.Forms.Form>y las instancias de matriz.  
  
 Si una variable almacena un puntero a una instancia de una clase que no se conocen en tiempo de compilación, o si puede señalar a los datos de diversos tipos de datos, declárelo como `Object`.  
  
 La ventaja de la `Object` es de tipo de datos que puede usar para almacenar datos de cualquier tipo de datos. La desventaja es que se incurre en operaciones adicionales que llevará más tiempo de ejecución y hacer que su aplicación se ejecuta más lentamente. Si usa un `Object` variables para tipos de valor, se incurre en *boxing* y *unboxing*. Si desea usarla para tipos de referencia, se incurre en *enlace más tarde*.  
  
## <a name="see-also"></a>Vea también
- [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
