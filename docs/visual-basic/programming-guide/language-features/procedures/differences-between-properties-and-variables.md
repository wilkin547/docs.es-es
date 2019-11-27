---
title: Diferencias entre propiedades y variables
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: bbed3248840803d36607a67c8373fed15c07445f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341219"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Diferencias entre propiedades y variables en Visual Basic
Las variables y las propiedades representan valores a los que se puede tener acceso. Sin embargo, hay diferencias en el almacenamiento y la implementación.  
  
## <a name="variables"></a>Variables  
 Una *variable* corresponde directamente a una ubicación de memoria. Una variable se define con una instrucción de declaración única. Una variable puede ser una *variable local*, definida dentro de un procedimiento y disponible solo dentro de ese procedimiento, o puede ser una *variable miembro*, definida en un módulo, clase o estructura, pero no dentro de ningún procedimiento. Una variable miembro también se denomina *campo*.  
  
## <a name="properties"></a>Propiedades  
 Una *propiedad* es un elemento de datos definido en un módulo, clase o estructura. Una propiedad se define con un bloque de código entre las instrucciones `Property` y `End Property`. El bloque de código contiene un procedimiento `Get`, un `Set` procedimiento o ambos. Estos procedimientos se denominan *procedimientos de propiedad* o *descriptores de acceso de propiedad*. Además de recuperar o almacenar el valor de la propiedad, también pueden realizar acciones personalizadas, como actualizar un contador de acceso.  
  
## <a name="differences"></a>Diferencias  
 En la tabla siguiente se muestran algunas diferencias importantes entre las variables y las propiedades.  
  
|Punto de diferencia|Variable|Propiedad|  
|-------------------------|--------------|--------------|  
|Declaración|Instrucción de declaración única|Series de instrucciones en un bloque de código|  
|Implementación|Ubicación de almacenamiento único|Código ejecutable (procedimientos de propiedad)|  
|Almacenamiento|Asociado directamente al valor de la variable|Normalmente, el almacenamiento interno no está disponible fuera de la clase o módulo que contiene la propiedad.<br /><br /> El valor de la propiedad puede existir o no como un elemento almacenado <sup>1</sup>|  
|Código ejecutable|Ninguno|Debe tener al menos un procedimiento.|  
|Acceso de lectura y escritura|Lectura/escritura o solo lectura|Lectura/escritura, solo lectura o solo escritura|  
|Acciones personalizadas (además de aceptar o devolver el valor)|No es posible|Puede realizarse como parte de la configuración o la recuperación de un valor de propiedad.|  
  
 <sup>1</sup> a diferencia de una variable, el valor de una propiedad podría no corresponder directamente con un solo elemento de almacenamiento. El almacenamiento podría dividirse en partes por comodidad o seguridad, o el valor podría almacenarse en un formato cifrado. En estos casos, el procedimiento `Get` ensamblaría las partes o descifrar el valor almacenado, y el procedimiento `Set` cifraría el nuevo valor o lo dividiría en el almacenamiento constituyente. Un valor de propiedad puede ser efímero, como la hora del día, en cuyo caso el procedimiento `Get` lo calcularía sobre la marcha cada vez que se tiene acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Crear una propiedad](./how-to-create-a-property.md)
- [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
