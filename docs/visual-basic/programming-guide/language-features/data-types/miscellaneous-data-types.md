---
title: Tipos de datos variados (Visual Basic) | Documentos de Microsoft
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
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 2de377fa9dfd7ec13cdbb9b700f8485b0c0e2106
ms.lasthandoff: 03/13/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipos de datos variados (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona varios tipos de datos que no están orientados a números o caracteres. En su lugar, tratan con datos especializados como Sí o no valores, valores de fecha y hora y direcciones de objetos.  
  
 Para una tabla que muestra una comparación en paralelo de la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipos de datos, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Tipo booleano  
 El [tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) es un valor sin signo que se interpreta como `True` o `False`. Ancho de sus datos depende de la plataforma de implementación. Si una variable puede contener sólo valores de dos estados como verdadero/falso, sí/no o activado/desactivado, declárela como `Boolean`.  
  
## <a name="date-type"></a>Date (tipo)  
 El [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene la información de fecha y hora. Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el principio (12:00 A.M.) del 1 de enero del año 1 del calendario gregoriano. Si una variable puede contener un valor de fecha, un valor de hora o ambos, declárela como `Date`.  
  
## <a name="object-type"></a>Tipo de objeto  
 El [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md) es una dirección de 32 bits que señala a una instancia de objeto dentro de la aplicación o en alguna otra aplicación. Un `Object` variable puede hacer referencia a cualquier objeto de la aplicación reconoce o a datos de cualquier tipo de datos. Esto incluye tanto *los tipos de valor*, como `Integer`, `Boolean`e instancias de estructura, y *tipos de referencia*, que son instancias de objetos creados a partir de clases como `String` y <xref:System.Windows.Forms.Form>y las instancias de matriz.</xref:System.Windows.Forms.Form>  
  
 Si una variable almacena un puntero a una instancia de una clase que no se conocen en tiempo de compilación, o si puede señalar a datos de varios tipos de datos, se declara como `Object`.  
  
 La ventaja de la `Object` es de tipo de datos que puede utilizar para almacenar datos de cualquier tipo de datos. El inconveniente es que provoca operaciones adicionales que toman más tiempo de ejecución y que la aplicación se ejecute más lentamente. Si utiliza un `Object` variables con tipos de valor, se incurre en *boxing* y *unboxing*. Si utiliza tipos de referencia, se incurre en *enlace más tarde*.  
  
## <a name="see-also"></a>Vea también  
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
