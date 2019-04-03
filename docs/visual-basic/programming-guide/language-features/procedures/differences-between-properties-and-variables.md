---
title: Diferencias entre propiedades y variables en Visual Basic
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
ms.openlocfilehash: de4800e23519c2cc1c8b2b219287b9fa018b9bbf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842907"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Diferencias entre propiedades y variables en Visual Basic
Variables y propiedades representan valores que puede tener acceso. Sin embargo, hay diferencias en el almacenamiento y la implementación.  
  
## <a name="variables"></a>Variables  
 Un *variable* corresponde directamente a una ubicación de memoria. Definir una variable con una única instrucción de declaración. Una variable puede ser un *variable local*, definido dentro de un procedimiento y solo está disponible en ese procedimiento, o puede ser un *variable miembro*, definidos en un módulo, clase o estructura, pero no dentro de cualquiera procedimiento. Una variable miembro también se denomina un *campo*.  
  
## <a name="properties"></a>Propiedades  
 Un *propiedad* es un elemento de datos definido en un módulo, clase o estructura. Definir una propiedad con un bloque de código entre la `Property` y `End Property` instrucciones. El bloque de código contiene un `Get` procedimiento, una `Set` procedimiento, o ambos. Estos procedimientos se denominan *procedimientos de propiedad* o *descriptores de acceso de propiedad*. Además de recuperar o almacenar el valor de propiedad, también pueden realizar acciones personalizadas, como la actualización de un contador de acceso.  
  
## <a name="differences"></a>Diferencias  
 En la tabla siguiente muestra algunas diferencias importantes entre las variables y propiedades.  
  
|Punto de diferencia|Variable|Property|  
|-------------------------|--------------|--------------|  
|Declaración|Instrucción de declaración única|Serie de instrucciones en un bloque de código|  
|Implementación|Ubicación de almacenamiento único|Código ejecutable (procedimientos de propiedad)|  
|Almacenamiento|Asociados directamente con el valor de la variable|Normalmente tiene almacenamiento interno no está disponible fuera de la propiedad de la clase contenedora o módulo<br /><br /> El valor de propiedad podría existir o no como un elemento almacenado <sup>1</sup>|  
|Código ejecutable|Ninguna|Debe tener al menos un procedimiento|  
|Acceso de lectura y escritura|Lectura/escritura o de solo lectura|Lectura/escritura, de solo lectura o solo escritura|  
|Acciones personalizadas (además de Aceptar o devolver un valor)|No es posible|Se pueden realizar como parte de la configuración o recuperar el valor de propiedad|  
  
 <sup>1</sup> a diferencia de una variable, el valor de una propiedad no es posible que corresponden directamente a un único elemento de almacenamiento. El almacenamiento puede dividirse en partes para mayor comodidad o seguridad, o el valor se puede almacenar en un formato cifrado. En estos casos el `Get` podría ensamblar los elementos o descifrar el valor almacenado, procedimiento y la `Set` procedimiento podría cifrar el valor nuevo o dividirla en el almacenamiento constituyente. Un valor de propiedad podría ser transitorios, como la hora del día, en cuyo caso el `Get` procedimiento lo calcularía sobre la marcha cada vez que se tiene acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Cómo: Crear una propiedad](./how-to-create-a-property.md)
- [Cómo: Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Cómo: Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Cómo: Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Cómo: Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
