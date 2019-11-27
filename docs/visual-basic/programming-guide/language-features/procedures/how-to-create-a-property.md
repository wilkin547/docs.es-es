---
title: 'Cómo: Crear una propiedad'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: ee5a9f687765ce064eb3c3f84218ed36eb916d9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349708"
---
# <a name="how-to-create-a-property-visual-basic"></a>Cómo: Crear una propiedad (Visual Basic)
Puede incluir una definición de propiedad entre una instrucción `Property` y una instrucción `End Property`. Dentro de esta definición se define un procedimiento de `Get`, un procedimiento de `Set` o ambos. Todo el código de la propiedad se encuentra dentro de estos procedimientos.  
  
 El procedimiento `Get` recupera el valor de la propiedad y el procedimiento `Set` almacena un valor. Si desea que la propiedad tenga acceso de lectura y escritura, debe definir ambos procedimientos. En el caso de una propiedad de solo lectura, solo se definen `Get`y, para una propiedad de solo escritura, solo se definen `Set`.  
  
### <a name="to-create-a-property"></a>Para crear una propiedad  
  
1. Fuera de cualquier propiedad o procedimiento, utilice una [instrucción de propiedad](../../../../visual-basic/language-reference/statements/property-statement.md), seguida de una instrucción `End Property`.  
  
2. Si la propiedad toma parámetros, siga la palabra clave `Property` con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.  
  
3. Siga los paréntesis con una cláusula `As` para especificar el tipo de datos del valor de la propiedad. Debe especificar el tipo de datos incluso para una propiedad de solo escritura.  
  
4. Agregue `Get` y `Set` procedimientos, según corresponda. Vea las instrucciones siguientes.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Para crear un procedimiento Get que recupere un valor de propiedad  
  
1. Entre las instrucciones `Property` y `End Property`, escriba una [instrucción Get](../../../../visual-basic/language-reference/statements/get-statement.md)seguida de una instrucción `End Get`. No es necesario definir ningún parámetro para el procedimiento `Get`.  
  
2. Coloque las instrucciones de código para recuperar el valor de la propiedad entre las instrucciones `Get` y `End Get`. Este código puede incluir otros cálculos y manipulaciones de datos, además de generar y devolver el valor de la propiedad.  
  
3. Use una instrucción `Return` para devolver el valor de la propiedad al código de llamada.  
  
 Debe escribir una `Get` procedimiento para una propiedad de lectura y escritura y para una propiedad de solo lectura. No debe definir un procedimiento `Get` para una propiedad de solo escritura.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Para crear un procedimiento set que escriba el valor de una propiedad  
  
1. Entre las instrucciones `Property` y `End Property`, escriba una [instrucción set](../../../../visual-basic/language-reference/statements/set-statement.md)seguida de una instrucción `End Set`.  
  
2. En la instrucción `Set`, siga la palabra clave `Set` con una lista de parámetros entre paréntesis. Esta lista de parámetros debe incluir al menos un parámetro de valor para el valor pasado por el código de llamada. El nombre predeterminado de este parámetro de valor es `Value`, pero puede usar otro nombre si es necesario. El parámetro de valor debe tener el mismo tipo de datos que la propiedad en sí.  
  
3. Coloque las instrucciones de código para almacenar un valor en la propiedad entre las instrucciones `Set` y `End Set`. Este código puede incluir otros cálculos y manipulaciones de datos, además de validar y almacenar el valor de la propiedad.  
  
4. Use el parámetro value para aceptar el valor proporcionado por el código de llamada. Puede almacenar este valor directamente en una instrucción de asignación o usarlo en una expresión para calcular el valor interno que se va a almacenar.  
  
 Debe escribir una `Set` procedimiento para una propiedad de lectura y escritura y para una propiedad de solo escritura. No debe definir un procedimiento `Set` para una propiedad de solo lectura.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una propiedad de lectura y escritura que almacena un nombre completo como dos nombres constituyentes, el nombre y el apellido. Cuando el código de llamada Lee `fullName`, el procedimiento `Get` combina los dos nombres constituyentes y devuelve el nombre completo. Cuando el código de llamada asigna un nuevo nombre completo, el procedimiento `Set` intenta dividirlo en dos nombres constituyentes. Si no encuentra un espacio, lo almacena como el nombre.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 En el ejemplo siguiente se muestran las llamadas típicas a los procedimientos de propiedad de `fullName`. La primera llamada establece el valor de la propiedad y la segunda llamada lo recupera.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
