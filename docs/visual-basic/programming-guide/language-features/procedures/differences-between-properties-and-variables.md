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
ms.openlocfilehash: 126e4baa2752ba7ccb5e8ff7b06a44839c1d0af2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Diferencias entre propiedades y variables en Visual Basic
Las variables y propiedades representan valores que puede tener acceso. Sin embargo, hay diferencias en el almacenamiento y la implementación.  
  
## <a name="variables"></a>Variables  
 A *variable* corresponde directamente a una ubicación de memoria. Definir una variable con una única instrucción de declaración. Una variable puede ser un *variable local*, definido dentro de un procedimiento y está disponible solo en ese procedimiento, o puede ser un *variable miembro*, definidos en un módulo, clase o estructura, pero no dentro de cualquiera procedimiento. Una variable de miembro también se denomina un *campo*.  
  
## <a name="properties"></a>Propiedades  
 A *propiedad* es un elemento de datos definido en un módulo, clase o estructura. Definir una propiedad con un bloque de código entre la `Property` y `End Property` las instrucciones. El bloque de código contiene un `Get` procedimiento, un `Set` procedimiento, o ambos. Estos procedimientos se denominan *property (procedimientos)* o *descriptores de acceso de propiedad*. Además de recuperar o almacenar el valor de propiedad, también pueden realizar las acciones personalizadas, como actualizar un contador de acceso.  
  
## <a name="differences"></a>Diferencias  
 En la tabla siguiente muestra algunas diferencias importantes entre las variables y propiedades.  
  
|Punto de diferencia|Variable|Property|  
|-------------------------|--------------|--------------|  
|Declaración|Única instrucción de declaración|Serie de instrucciones en un bloque de código|  
|Implementación|Ubicación de almacenamiento único|Código ejecutable (procedimientos de propiedades)|  
|Almacenamiento|Se asocian directamente con el valor de la variable|Normalmente tiene almacenamiento interno no está disponible fuera de la clase o módulo contenedor de la propiedad<br /><br /> Valor de la propiedad podría existir o no como un elemento almacenado <sup>1</sup>|  
|Código ejecutable|Ninguna|Debe tener al menos un procedimiento|  
|Acceso de lectura y escritura|Lectura/escritura o de solo lectura|Lectura y escritura, de solo lectura o de solo escritura|  
|Acciones personalizadas (además de Aceptar o devolver un valor)|No es posible|Se puede realizar como parte de la configuración ni la recuperación de valor de propiedad|  
  
 <sup>1</sup> a diferencia de una variable, el valor de una propiedad podría no corresponderse directamente a un único elemento de almacenamiento. El almacenamiento podría dividirse en partes por comodidad o seguridad, o el valor podría almacenarse en un formato cifrado. En estos casos el `Get` procedimiento podría ensamblar los elementos o descifrar el valor almacenado y el `Set` procedimiento podría cifrar el nuevo valor o dividir en el almacenamiento que lo componen. Un valor de propiedad podría ser efímero, como una hora del día, en cuyo caso el `Get` procedimiento lo calcularía sobre la marcha cada vez que se tiene acceso a la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Crear una propiedad](./how-to-create-a-property.md)  
 [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)  
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)  
 [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
