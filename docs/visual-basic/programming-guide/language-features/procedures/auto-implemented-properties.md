---
title: Propiedades autoimplementadas
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: f50b1f40ef9843391c6622561bfd8a8eaae6fc17
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090059"
---
# <a name="auto-implemented-properties-visual-basic"></a>Propiedades implementadas automáticamente (Visual Basic)

*Las propiedades implementadas automáticamente* permiten especificar rápidamente una propiedad de una clase sin tener que escribir código en `Get` y `Set` la propiedad. Al escribir código para una propiedad implementada automáticamente, el compilador de Visual Basic crea de manera automática un campo privado para almacenar la variable de propiedad, además de crear los procedimientos `Get` y `Set` asociados.  
  
 Con las propiedades implementadas automáticamente, una propiedad (incluido un valor predeterminado) puede declararse en una sola línea. En el ejemplo siguiente se muestran tres declaraciones de propiedad.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 Una propiedad implementada automáticamente equivale a una propiedad cuyo valor se almacena en un campo privado. En el siguiente ejemplo de código se muestra una propiedad implementada automáticamente.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 En el ejemplo de código siguiente se muestra el código equivalente al del ejemplo anterior de propiedad implementada automáticamente.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 En el código siguiente se muestran las propiedades de solo lectura implementadoras:  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 Se pueden realizar asignaciones a la propiedad con expresiones de inicialización, como se muestra en el ejemplo, o se pueden realizar asignaciones a las propiedades en el constructor del tipo contenedor.  Siempre que lo desee, puede realizar asignaciones a los campos de respaldo de propiedades de solo lectura.  
  
## <a name="backing-field"></a>Campo de respaldo  

 Cuando se declara una propiedad implementada automáticamente, Visual Basic crea automáticamente un campo privado oculto denominado *campo de respaldo* para contener el valor de la propiedad. El nombre del campo de respaldo es el nombre de la propiedad implementada automáticamente precedido por un carácter de subrayado (_). Por ejemplo, si declara una propiedad implementada automáticamente denominada `ID`, el campo de respaldo se denominará `_ID`. Si se incluye un miembro de la clase que también se denomina `_ID`, se produce un conflicto de nomenclatura y Visual Basic informa de un error del compilador.  
  
 El campo de respaldo también tiene las siguientes características:  
  
- El modificador de acceso del campo de respaldo siempre es `Private`, incluso cuando la misma propiedad tiene un nivel de acceso diferente, como `Public`.  
  
- Si la propiedad está marcada como `Shared`, también se comparte el campo de respaldo.  
  
- Los atributos especificados para la propiedad no se aplican al campo de respaldo.  
  
- El acceso al campo de respaldo se puede realizar desde el código contenido en la clase y desde herramientas de depuración como la ventana Inspección.  Sin embargo, dicho campo no se muestra en una lista de finalización de palabras de IntelliSense.  
  
## <a name="initializing-an-auto-implemented-property"></a>Inicializar una propiedad implementada automáticamente  

 Cualquier expresión que se pueda usar para inicializar un campo es válida para inicializar una propiedad implementada automáticamente. Al inicializar una propiedad implementada automáticamente, la expresión se evalúa y se pasa al procedimiento `Set` para la propiedad. En los ejemplos de código siguientes se muestran algunas propiedades implementadas automáticamente que incluyen valores iniciales.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 No se puede inicializar una propiedad implementada automáticamente que sea miembro de una `Interface` o que esté marcada como `MustOverride`.  
  
 Al declarar una propiedad implementada automáticamente como miembro de una `Structure`, solo se puede inicializar la propiedad implementada automáticamente si se marca como `Shared`.  
  
 Al declarar una propiedad implementada automáticamente como matriz, no se pueden especificar límites de matriz explícitos. Sin embargo, se puede proporcionar un valor con un inicializador de matriz, como se muestra en los ejemplos siguientes.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a>Definiciones de propiedades que requieren sintaxis estándar  

 Las propiedades implementadas automáticamente son fáciles de usar y admiten muchos escenarios de programación. Sin embargo, hay situaciones en las que no se puede usar una propiedad implementada automáticamente y, en su lugar, se debe usar la sintaxis de propiedades estándar o *expandida*.  
  
 Si desea realizar una de las acciones siguientes, tiene que usar la sintaxis de definición de propiedades expandidas:  
  
- Agregar código al procedimiento `Get` o `Set` de una propiedad, como código para validar los valores de entrada del procedimiento `Set`. Por ejemplo, puede que desee comprobar si una cadena que representa un número de teléfono contiene la cantidad de números necesaria antes de establecer el valor de propiedad.  
  
- Especificar distintos tipos de accesibilidad para los procedimientos `Get` y `Set`. Por ejemplo, puede que desee establecer el procedimiento `Set` como `Private` y el procedimiento `Get` como `Public`.  
  
- Crear propiedades de tipo `WriteOnly`.  
  
- Usar propiedades parametrizadas (incluidas las propiedades `Default`). Debe declarar una propiedad expandida para especificar un parámetro para la propiedad o para especificar parámetros adicionales para el procedimiento `Set`.  
  
- Colocar un atributo en el campo de respaldo o cambiar el nivel de acceso del campo de respaldo.  
  
- Proporcionar comentarios XML para el campo de respaldo.  
  
## <a name="expanding-an-auto-implemented-property"></a>Expandir una propiedad implementada automáticamente  

 Si tiene que convertir una propiedad implementada automáticamente en una propiedad expandida que contiene un procedimiento `Get` o `Set`, el Editor de código de Visual Basic puede generar automáticamente los procedimientos `Get` y `Set` y la instrucción `End Property` para la propiedad. El código se genera si coloca el cursor en una línea en blanco después de la `Property` instrucción, escriba `G` (para `Get` ) o `S` (para `Set` ) y presione Entrar. El Editor de código de Visual Basic genera automáticamente el procedimiento `Get` o `Set` para las propiedades de solo lectura y de solo escritura al presionar ENTRAR al final de una instrucción `Property`.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [ReadOnly](../../../language-reference/modifiers/readonly.md)
- [WriteOnly](../../../language-reference/modifiers/writeonly.md)
- [Objetos y clases](../objects-and-classes/index.md)
