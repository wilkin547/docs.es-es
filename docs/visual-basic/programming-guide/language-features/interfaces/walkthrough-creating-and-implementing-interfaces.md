---
title: Crear e implementar Interfaces (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: af9305deb60637b642d091501e743f2c7a57ccad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653616"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Tutorial: Crear e implementar interfaces (Visual Basic)

Interfaces describen las características de propiedades, métodos y eventos, pero dejan los detalles de implementación para las estructuras o clases.  
  
 Este tutorial muestra cómo declarar e implementar una interfaz.  
  
> [!NOTE]
>  En este tutorial no proporciona información sobre cómo crear una interfaz de usuario.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Para definir una interfaz
  
1.  Abra un proyecto Aplicación Windows de Visual Basic nuevo.  
  
2.  Agregar un nuevo módulo al proyecto haciendo clic en **Agregar módulo** en el **proyecto** menú.  
  
3.  Nombre del nuevo módulo `Module1.vb` y haga clic en **agregar**. Se muestra el código para el nuevo módulo.  
  
4.  Defina una interfaz denominada `TestInterface` en `Module1` escribiendo `Interface TestInterface` entre el `Module` y `End Module` instrucciones y, a continuación, presione ENTRAR. El **Editor de código** sangrías el `Interface` (palabra clave) y agrega un `End Interface` instrucción para formar un bloque de código.  
  
5.  Definir una propiedad, el método y el evento para la interfaz, coloque el código siguiente entre las `Interface` y `End Interface` instrucciones:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementación

 Puede observar que la sintaxis utilizada para declarar a los miembros de interfaz es diferente de la sintaxis utilizada para declarar a miembros de clase. Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.  
  
### <a name="to-implement-the-interface"></a>Para implementar la interfaz
  
1.  Agregue una clase denominada `ImplementationClass` agregando la siguiente instrucción para `Module1`, después la `End Interface` instrucción pero antes del `End Module` instrucción y, a continuación, presione ENTRAR:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** proporciona una coincidencia `End Class` instrucción cuando se presiona ENTRAR.  
  
2.  Agregue el siguiente `Implements` instrucción `ImplementationClass`, que la interfaz de un nombre a la clase implementa:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Cuando se muestra por separado de otros elementos en la parte superior de una clase o estructura, el `Implements` instrucción indica que la clase o estructura implementa una interfaz.  
  
     Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos por `TestInterface` cuando se presiona ENTRAR, y puede omitir el paso siguiente.  
  
3.  Si no está trabajando en el entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface`. Agregue el código siguiente a `ImplementationClass` implementar `Event1`, `Method1`, y `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     El `Implements` designadas por la interfaz y el miembro de interfaz que se implementa la instrucción.  
  
4.  Completar la definición de `Prop1` mediante la adición de un campo privado a la clase que almacena el valor de propiedad:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Devolver el valor de la `pval` de la propiedad de descriptor de acceso get.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Establezca el valor de `pval` en la propiedad de descriptor de acceso set.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  Completar la definición de `Method1` agregando el código siguiente.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Para probar la implementación de la interfaz
  
1.  Haga clic en el formulario de inicio para el proyecto en el **el Explorador de soluciones**y haga clic en **ver código**. El editor muestra la clase para el formulario de inicio. De forma predeterminada, el formulario de inicio se denomina `Form1`.  
  
2.  Agregue el siguiente `testInstance` campo el `Form1` clase:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Mediante la declaración de `testInstance` como `WithEvents`, la `Form1` clase puede controlar sus eventos.  
  
3.  Agregue el siguiente controlador de eventos para el `Form1` clase para controlar los eventos generados por `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  Agregue una subrutina denominada `Test` a la `Form1` clase para probar la clase de implementación:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     El `Test` procedimiento crea una instancia de la clase que implementa `MyInterface`, asigna esa instancia a la `testInstance` campo, Establece una propiedad y ejecuta un método a través de la interfaz.  
  
5.  Agregue código para llamar a la `Test` procedimiento desde la `Form1 Load` procedimiento con el formulario de inicio:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  Ejecute el `Test` procedimiento presionando F5. Se muestra el mensaje "Prop1 se establece en 9". Después de hacer clic en Aceptar, el mensaje "el parámetro X de Method1 es 5" se muestran. Haga clic en Aceptar, y se muestra el mensaje "el controlador de eventos ha interceptado el evento".  
  
## <a name="see-also"></a>Vea también

 [Implements (instrucción)](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Interface (instrucción)](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md)  