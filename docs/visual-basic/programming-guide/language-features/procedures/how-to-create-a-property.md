---
title: Filtrar Crear una propiedad (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 91f34de36e88724ccab21097bf54a4604f7eee37
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306721"
---
# <a name="how-to-create-a-property-visual-basic"></a>Filtrar Crear una propiedad (Visual Basic)
Incluya una definición de propiedad entre un `Property` instrucción y un `End Property` instrucción. Dentro de esta definición se define un `Get` procedimiento, una `Set` procedimiento, o ambos. Código de la de la propiedad se encuentra dentro de estos procedimientos.  
  
 El `Get` procedimiento recupera el valor de propiedad y el `Set` procedimiento almacena un valor. Si desea que la propiedad para tener acceso de lectura y escritura, debe definir ambos procedimientos. Para una propiedad de solo lectura, definir solo `Get`, y para una propiedad de solo escritura, puede definir solo `Set`.  
  
### <a name="to-create-a-property"></a>Para crear una propiedad  
  
1. Fuera de cualquier propiedad o procedimiento, utilice un [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), seguido de un `End Property` instrucción.  
  
2. Si la propiedad acepta parámetros, siga el `Property` palabra clave con el nombre del procedimiento y, después, en la lista de parámetros entre paréntesis.  
  
3. Siga los paréntesis con un `As` cláusula para especificar el tipo de datos del valor de propiedad. Debe especificar el tipo de datos, incluso para una propiedad de solo escritura.  
  
4. Agregar `Get` y `Set` procedimientos, según corresponda. Consulte las instrucciones siguientes.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Para crear un procedimiento Get que recupera un valor de propiedad  
  
1. Entre los `Property` y `End Property` instrucciones, escribir un [instrucción Get](../../../../visual-basic/language-reference/statements/get-statement.md), seguido de un `End Get` instrucción. No es necesario definir los parámetros para el `Get` procedimiento.  
  
2. Coloque las instrucciones de código para recuperar el valor de propiedad entre el `Get` y `End Get` instrucciones. Este código puede incluir otros cálculos y manipulaciones de datos además de generar y devolver el valor de propiedad.  
  
3. Use un `Return` instrucción para devolver el valor de propiedad al código de llamada.  
  
 Debe escribir un `Get` procedimiento para una propiedad de lectura y escritura y para una propiedad de solo lectura. No debe definir un `Get` procedimiento para una propiedad de solo escritura.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Para crear un procedimiento Set que escribe un valor de propiedad  
  
1. Entre el `Property` y `End Property` instrucciones, escribir un [instrucción Set](../../../../visual-basic/language-reference/statements/set-statement.md), seguido de un `End Set` instrucción.  
  
2. En el `Set` (instrucción), siga el `Set` palabra clave con una lista de parámetros entre paréntesis. Esta lista de parámetros debe incluir al menos un parámetro de valor para el valor pasado por el código de llamada. El nombre predeterminado para este parámetro de valor es `Value`, pero puede usar un nombre diferente si es necesario. El valor del parámetro debe tener los mismos datos de tipo que la propiedad propiamente dicha.  
  
3. Coloque las instrucciones de código para almacenar un valor en la propiedad entre la `Set` y `End Set` instrucciones. Este código puede incluir otros cálculos y manipulaciones de datos además de validar y almacenar el valor de propiedad.  
  
4. Utilice el valor del parámetro para aceptar el valor proporcionado por el código de llamada. Puede almacenar este valor directamente en una instrucción de asignación o usarla en una expresión para calcular el valor interno que se almacenará.  
  
 Debe escribir un `Set` procedimiento para una propiedad de lectura y escritura y para una propiedad de solo escritura. No debe definir un `Set` procedimiento para una propiedad de solo lectura.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea una propiedad de lectura/escritura que almacena un nombre completo como dos nombres constitutivos, el nombre y el apellido. Cuando se lee el código de llamada `fullName`, el `Get` procedimiento combina los dos nombres constituyentes y devuelve el nombre completo. Cuando el código de llamada asigna un nuevo nombre completo, el `Set` procedimiento intenta dividir en dos nombres constitutivos. Si no encuentra un espacio, almacena como el nombre.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 El ejemplo siguiente muestra las llamadas típicas a los procedimientos de propiedad de `fullName`. La primera llamada establece el valor de propiedad y la segunda llamada lo recupera.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Filtrar para declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Filtrar para llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Filtrar Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Filtrar para establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Filtrar para obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
