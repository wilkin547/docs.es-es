---
title: Tipos de datos varios
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 45b44abc24b968f19b456cbe0be0f25efc8f0ce8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095465"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipos de datos variados (Visual Basic)

Visual Basic proporciona varios tipos de datos que no están orientados a números o caracteres. En su lugar, se ocupan de los datos especializados, como los valores sí/no, los valores de fecha y hora y las direcciones de objeto.  
  
 Para ver una tabla que muestra una comparación en paralelo de los tipos de datos Visual Basic, vea [tipos de datos](../../../language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Tipo booleano  

 El [tipo de datos Boolean](../../../language-reference/data-types/boolean-data-type.md) es un valor sin signo que se interpreta como `True` o `False` . El ancho de los datos depende de la plataforma de implementación. Si una variable solo puede contener valores de dos Estados, como true/false, yes/no o ON/OFF, declárela como `Boolean` .  
  
## <a name="date-type"></a>Tipo de fecha  

 El [tipo de datos Date](../../../language-reference/data-types/date-data-type.md) es un valor de 64 bits que contiene información de fecha y hora. Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el inicio (12:00 A.M.) del 1 de enero del año 1 del calendario gregoriano. Si una variable puede contener un valor de fecha, un valor de hora o ambos, declárelo como `Date` .  
  
## <a name="object-type"></a>Tipo de objeto  

 El [tipo de datos Object](../../../language-reference/data-types/object-data-type.md) es una dirección de 32 bits que apunta a una instancia de objeto dentro de la aplicación o en alguna otra aplicación. Una `Object` variable puede hacer referencia a cualquier objeto que la aplicación reconozca o a datos de cualquier tipo de datos. Esto incluye los dos *tipos de valor*, como `Integer` , `Boolean` y las instancias de la estructura, y los *tipos de referencia*, que son instancias de los objetos creados a partir de clases como `String` y <xref:System.Windows.Forms.Form> , y instancias de matriz.  
  
 Si una variable almacena un puntero a una instancia de una clase que no conoce en tiempo de compilación, o si puede apuntar a datos de varios tipos de datos, declárelo como `Object` .  
  
 La ventaja del `Object` tipo de datos es que se puede usar para almacenar datos de cualquier tipo de datos. El inconveniente es que se incurre en operaciones adicionales que tardan más tiempo de ejecución y hacen que la aplicación funcione más lentamente. Si utiliza una `Object` variable para los tipos de valor, incurrirá en la *conversión boxing* y la conversión *unboxing*. Si se usa para los tipos de referencia, se incurre en el *enlace en tiempo de ejecución*.  
  
## <a name="see-also"></a>Vea también

- [Caracteres de tipo](type-characters.md)
- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de datos numéricos](numeric-data-types.md)
- [Tipos de datos de caracteres](character-data-types.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](../early-late-binding/index.md)
