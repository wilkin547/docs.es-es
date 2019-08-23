---
title: Crear e implementar interfaces (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 62e301e9eb366d14b58088d3e2cda3b567d17f5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923317"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Tutorial: Crear e implementar interfaces (Visual Basic)

Las interfaces describen las características de las propiedades, los métodos y los eventos, pero dejan los detalles de la implementación hasta estructuras o clases.  
  
 En este tutorial se muestra cómo declarar e implementar una interfaz.  
  
> [!NOTE]
> En este tutorial no se proporciona información sobre cómo crear una interfaz de usuario.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Para definir una interfaz
  
1. Abra un proyecto Aplicación Windows de Visual Basic nuevo.  
  
2. Agregue un nuevo módulo al proyecto haciendo clic en **Agregar módulo** en el menú **proyecto** .  
  
3. Asigne un nombre al `Module1.vb` nuevo módulo y haga clic en **Agregar**. Se muestra el código para el nuevo módulo.  
  
4. Defina una interfaz denominada `TestInterface` dentro `Module1` de escribiendo `Interface TestInterface` entre las `Module` instrucciones `End Module` y y, a continuación, presione Entrar. El **Editor de código** aplica sangría a `Interface` la palabra clave y `End Interface` agrega una instrucción para formar un bloque de código.  
  
5. Defina una propiedad, un método y un evento para la interfaz colocando el siguiente código `Interface` entre `End Interface` las instrucciones y:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementación

 Es posible que observe que la sintaxis usada para declarar miembros de interfaz es diferente de la sintaxis utilizada para declarar miembros de clase. Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.  
  
### <a name="to-implement-the-interface"></a>Para implementar la interfaz
  
1. Agregue una clase denominada `ImplementationClass` agregando la siguiente instrucción a `Module1`, después de `End Interface` la instrucción, pero `End Module` antes de la instrucción y, a continuación, presione ENTRAR:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Si está trabajando en el entorno de desarrollo integrado, el **Editor de código** proporciona una `End Class` instrucción coincidente al presionar entrar.  
  
2. Agregue la siguiente `Implements` instrucción a `ImplementationClass`, que nombra la interfaz que la clase implementa:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Cuando se enumeran por separado de otros elementos en la parte superior de una clase o `Implements` estructura, la instrucción indica que la clase o estructura implementa una interfaz.  
  
     Si está trabajando en el entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos `TestInterface` por al presionar entrar, y puede omitir el paso siguiente.  
  
3. Si no está trabajando en el entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface`. Agregue el código siguiente a `ImplementationClass` para implementar `Event1`, `Method1`y `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     La `Implements` instrucción nombra la interfaz y el miembro de interfaz que se está implementando.  
  
4. Complete la definición de `Prop1` agregando un campo privado a la clase que almacenó el valor de propiedad:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Devuelva el valor de `pval` desde el descriptor de acceso get de la propiedad.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Establezca el valor de `pval` en el descriptor de acceso set de propiedad.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Agregue el código siguiente `Method1` para completar la definición de.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Para probar la implementación de la interfaz
  
1. Haga clic con el botón secundario en el formulario de inicio del proyecto en el **Explorador de soluciones**y haga clic en **Ver código**. El editor muestra la clase del formulario de inicio. De forma predeterminada, se llama `Form1`al formulario de inicio.  
  
2. Agregue el siguiente `testInstance` campo a la `Form1` clase:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Al declarar `testInstance` como `WithEvents`, la `Form1` clase puede controlar sus eventos.  
  
3. Agregue el siguiente controlador de eventos a `Form1` la clase para controlar los eventos `testInstance`generados por:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Agregue una subrutina denominada `Test` a la `Form1` clase para probar la clase de implementación:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     El `Test` procedimiento crea una instancia de la clase que `MyInterface`implementa, asigna esa instancia al `testInstance` campo, establece una propiedad y ejecuta un método a través de la interfaz.  
  
5. Agregue código para llamar `Test` al procedimiento desde el `Form1 Load` procedimiento del formulario de Inicio:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Ejecute el `Test` procedimiento presionando F5. Se muestra el mensaje "Prop1 se estableció en 9". Después de hacer clic en aceptar, se muestra el mensaje "el parámetro X de method1 es 5". Haga clic en aceptar y se mostrará el mensaje "el controlador de eventos detectó el evento".  
  
## <a name="see-also"></a>Vea también

- [Implements (instrucción)](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface (instrucción)](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md)
