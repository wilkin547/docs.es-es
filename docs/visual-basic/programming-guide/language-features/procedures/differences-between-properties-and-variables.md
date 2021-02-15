---
description: 'Más información sobre: diferencias entre propiedades y variables en Visual Basic'
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
ms.openlocfilehash: 6118d37616f3df1f21dda8e3a6392b6a6f37a24e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464721"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Diferencias entre propiedades y variables en Visual Basic

Las variables y las propiedades representan valores a los que se puede tener acceso. Sin embargo, hay diferencias en el almacenamiento y la implementación.  
  
## <a name="variables"></a>Variables  

 Una *variable* corresponde directamente a una ubicación de memoria. Una variable se define con una instrucción de declaración única. Una variable puede ser una *variable local*, definida dentro de un procedimiento y disponible solo dentro de ese procedimiento, o puede ser una *variable miembro*, definida en un módulo, clase o estructura, pero no dentro de ningún procedimiento. Una variable miembro también se denomina *campo*.  
  
## <a name="properties"></a>Propiedades  

 Una *propiedad* es un elemento de datos definido en un módulo, clase o estructura. Una propiedad se define con un bloque de código entre `Property` las `End Property` instrucciones y. El bloque de código contiene un `Get` procedimiento, un `Set` procedimiento o ambos. Estos procedimientos se denominan *procedimientos de propiedad* o *descriptores de acceso de propiedad*. Además de recuperar o almacenar el valor de la propiedad, también pueden realizar acciones personalizadas, como actualizar un contador de acceso.  
  
## <a name="differences"></a>Diferencias  

 En la tabla siguiente se muestran algunas diferencias importantes entre las variables y las propiedades.  
  
|Punto de diferencia|Variable|Propiedad|  
|-------------------------|--------------|--------------|  
|Declaración|Instrucción de declaración única|Series de instrucciones en un bloque de código|  
|Implementación|Ubicación de almacenamiento único|Código ejecutable (procedimientos de propiedad)|  
|Storage|Asociado directamente al valor de la variable|Normalmente, el almacenamiento interno no está disponible fuera de la clase o módulo que contiene la propiedad.<br /><br /> El valor de la propiedad puede existir o no como un elemento almacenado <sup>1</sup>|  
|Código ejecutable|Ninguno|Debe tener al menos un procedimiento.|  
|Acceso de lectura y escritura|Lectura/escritura o solo lectura|Lectura/escritura, solo lectura o solo escritura|  
|Acciones personalizadas (además de aceptar o devolver el valor)|No es posible|Puede realizarse como parte de la configuración o la recuperación de un valor de propiedad.|  
  
 <sup>1</sup> a diferencia de una variable, el valor de una propiedad podría no corresponder directamente con un solo elemento de almacenamiento. El almacenamiento podría dividirse en partes por comodidad o seguridad, o el valor podría almacenarse en un formato cifrado. En estos casos `Get` , el procedimiento ensamblará las partes o descifrará el valor almacenado, y el `Set` procedimiento cifrará el nuevo valor o lo dividirá en el almacenamiento constituyente. Un valor de propiedad puede ser efímero, como la hora del día, en cuyo caso el `Get` procedimiento lo calcularía sobre la marcha cada vez que se tiene acceso a la propiedad.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Instrucción Dim](../../../language-reference/statements/dim-statement.md)
- [Procedimiento para crear una propiedad](./how-to-create-a-property.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedimiento para llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedimiento para establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Procedimiento para obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
