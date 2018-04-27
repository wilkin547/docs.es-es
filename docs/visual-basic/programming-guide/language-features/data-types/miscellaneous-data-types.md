---
title: Tipos de datos variados (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipos de datos variados (Visual Basic)
Visual Basic proporciona varios tipos de datos que no están orientados a caracteres o números. En su lugar, tratan con datos especializado, como sí/no valores, valores de fecha/hora y direcciones de objetos.  
  
 Para una tabla que muestra una comparación en paralelo de los tipos de datos de Visual Basic, vea [tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="boolean-type"></a>Tipo booleano  
 El [tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) es un valor sin signo que se interpreta como `True` o `False`. Su ancho de datos depende de la plataforma de implementación. Si una variable puede contener sólo valores de dos estados como verdadero/falso, sí/no, o activado/desactivado, declárela como `Boolean`.  
  
## <a name="date-type"></a>Date (tipo)  
 El [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene información de fecha y hora. Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el principio (12:00 A.M.) del 1 de enero del año 1 del calendario gregoriano. Si una variable puede contener un valor de fecha, un valor de hora o ambas, declárelo como `Date`.  
  
## <a name="object-type"></a>Tipo de objeto  
 El [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md) es una dirección de 32 bits que señala a una instancia de objeto dentro de la aplicación o en otra aplicación. Un `Object` variable puede hacer referencia a cualquier objeto de la aplicación reconoce o a datos de cualquier tipo de datos. Esto incluye tanto *los tipos de valor*, como `Integer`, `Boolean`y las instancias de la estructura, y *hacen referencia a tipos*, que son instancias de objetos creados a partir de clases como `String`y <xref:System.Windows.Forms.Form>y la matriz de instancias.  
  
 Si una variable almacena un puntero a una instancia de una clase que no se conocen en tiempo de compilación, o si puede señalar a los datos de diversos tipos de datos, se declara como `Object`.  
  
 La ventaja de la `Object` es de tipo de datos que puede usar para almacenar datos de cualquier tipo de datos. La desventaja es que se incurre en operaciones adicionales que tardan más tiempo de ejecución y que la aplicación se ejecute más lentamente. Si utiliza un `Object` variables para tipos de valor, se incurre en *conversión boxing* y *unboxing*. Si utiliza tipos de referencia, se incurre en *enlace más tarde*.  
  
## <a name="see-also"></a>Vea también  
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
